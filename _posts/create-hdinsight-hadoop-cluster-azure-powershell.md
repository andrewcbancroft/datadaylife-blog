---
title: Create an HDInsight Hadoop Cluster in Azure with PowerShell
excerpt: "How do you create an HDInsight Hadoop cluster programmatically in Azure with PowerShell? Here, I walk through what you need to know and provide a sample script."
layout: work-in-progress
toc: true
categories: [Big Data, Hadoop, Azure, HDInsight]
---
Being able to programmatically create an HDInsight Hadoop cluster, use it, and subsequently tear it down so that you don't incur cost is one use-case for maximizing efficient use of Azure's cloud platform.

Here, I want to break the use-case down into chunks:

# Log in to Azure (PowerShell)
The first step is to log in to your Azure account:

```powershell
Login-AzureRmAccount
```

# Create a Resource Group
Resource Groups in Azure make it extremely convenient to package all of the pieces of your temporary, on-the-fly-use, HDInsight Hadoop cluster.  

The idea is to create the storage you need, along with the Hadoop cluster infrastructure you need, and stick them together inside of a resource group. Why? So that you can tear it all down once you're done in a single step by removing the resource group itself. Removing a resource group is how you can delete both the storage and the HDInsight Hadoop cluster all at once.

If you happened to want to keep the storage around, no worries.  HDInsight is the piece that can get expensive while it's online.  You can always resort to removing the HDInsight cluster *only*, if you're wanting to keep the storage, but save on costs while the Hadoop cluster isn't being utilized.

Om either case, the question remains:  What do you need to know in order to create a resouce group?

* The **name** of the resource group (you get to make this up)
* The **location** of the resource group (this is one of the Azure regions)

Once you've got these pieces, you can start a PowerShell script:

```powershell
Login-AzureRmAccount

##New Stuff##
$resourceGroupName = "nameOfResourceGroup" # Choose a name that represents what the group contains
$location = "South Central US"

# If you're not sure what the valid location names are, uncomment and run the line below.
# Use the DisplayName value in $location above.
# Get-AzureRmLocation | Format-Table

New-AzureRmResourceGroup -Name $resourceGroupName -Location $location
```

# Create Storage
Hadoop clusters need a storage area that they can use to store files and do processing.  For temporary clusters use on-the-fly, I like to create a new storage account in the newly-created resource group.  Alternatively, you can use an existing storage account.

What do you need in order to create and/or use storage in PowerShell?

* A **storage account**.  You can use an existing one, or create a new one just for this temporary-use cluster.  What do you need in order to create a new storage account?
  * A **name** for the storage account
  * A **resource group** where it'll live
  * A **type** (Premium_LRS, Standard_GRS, Standard_LRS, Standard_RAGRS, or Standard_ZRS)
  * A **location**.  You can reuse the `$location` variable you used to create a new resource group
* A **storage account key** to allow you to securely write to the storage area programmatically
* A **storage context**, which is basically a formal PowerShell "object" that made up of the storage account name and the storage account key
* A **container** within that storage context that should be used to store and process files in (you can make up a new **container name** and create one, or use an existing container in an existing storage account...)

Continuing with the PowerShell script now:

```powershell
Login-AzureRmAccount

$resourceGroupName = "nameOfResourceGroup" # Choose a name that represents what the group contains
$location = "South Central US"

# If you're not sure what the valid location names are, uncomment and run the line below.
# Use the DisplayName value in $location above.
# Get-AzureRmLocation | Format-Table

New-AzureRmResourceGroup -Name $resourceGroupName -Location $location

###New Stuff###
$storageAccountName = "$resourceGroupName" # You can choose any name you want - I name mine the same as my resource group for convenience
$containerName = "hdp$resourceGroupName" # I like to add "hdp" to the beginning of the resource group name

Write-Host "Creating storage account..."
New-AzureRmStorageAccount 
  -Name $storageAccountName `
  -ResourceGroupName $resourceGroupName `
  -Type Standard_GRS ` # Options are Premium_LRS, Standard_GRS, Standard_LRS, Standard_RAGRS, and Standard_ZRS
  -Location $location
 
Write-Host "Creating container..."
$storageAccountKey = (Get-AzureRmStorageAccountKey -ResourceGroupName $resourceGroupName -Name $storageAccountName).Value[0]
$context = New-AzureStorageContext -StorageAccountName $storageAccountName -StorageAccountKey $storageAccountKey
New-AzureStorageContainer -Name $containerName -Context $context
```
# Create the Hadoop Cluster

# Final Script
Before I call it "good", I like to bring my shared variables up to the top of the script so they're not sprinkled throughout.  Here's a final script that I use as a template for creating new HDInsight Hadoop clusters in Azure:

```powershell
Login-AzureRmAccount

$resourceGroupName = "nameOfResourceGroup"
$location = "South Central US"
$storageAccountName = "$resourceGroupName"
$containerName = "hdp$resourceGroupName"
$clusterName = $containerName
$clusterNodes = 2
$httpUserName = "HDUser"
$sshUserName = "SSHHuser"
$password = ConvertTo-SecureString "MyPa`$`$w0rD" -AsPlainText -Force
 
New-AzureRmResourceGroup -Name $resourceGroupName -Location $location
 
Write-Host "Creating storage account..."
New-AzureRmStorageAccount 
  -Name $storageAccountName `
  -ResourceGroupName $resourceGroupName `
  -Type Standard_GRS `
  -Location $location
 
Write-Host "Creating container..."
$storageAccountKey = (Get-AzureRmStorageAccountKey -ResourceGroupName $resourceGroupName -Name $storageAccountName).Value[0]
$context = New-AzureStorageContext -StorageAccountName $storageAccountName -StorageAccountKey $storageAccountKey
New-AzureStorageContainer -Name $containerName -Context $context
 
Write-Host "Creating HDInsight cluster..."
$httpCredential = New-Object System.Management.Automation.PSCredential ($httpUserName, $password)
$sshCredential = New-Object System.Management.Automation.PSCredential ($sshUserName, $password)
New-AzureRmHDInsightCluster 
  -ResourceGroupName $resourceGroupName `
  -ClusterName $clusterName `
  -ClusterType Hadoop `
  -Version 3.6 `
  -Location $location `
  -DefaultStorageAccountName "$storageAccountName.blob.core.windows.net" `
  -DefaultStorageAccountKey $storageAccountKey `
  -DefaultStorageContainer $containerName `
  -ClusterSizeInNodes $clusterNodes `
  -OSType Linux `
  -HttpCredential $httpCredential `
  -SshCredential $sshCredential
 
Write-Host "Finished!"
```
