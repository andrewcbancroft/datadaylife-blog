---
title: "Create a SQL Server Credential for Accessing Azure Blob Storage"
author: "Andrew Bancroft"
date:   2019-05-20
description: "PowerShell script for creating a SQL Server Credential to access Azure Blob Storage."
type: technical_note
draft: false
comments: true
---

## Prerequisites:

* The `SqlServer` PowerShell module must be installed.
  * Run `Install-Module -Name SqlServer` if you need to install it...

##### create-credential.ps1
{{< highlight powershell >}}
import-module SqlServer

$storageAccount = "<StorageAccountName>"  #replace this with your Azure storage account name
$storageKey = "<StorageAccountKey>"  #replace this with one of your Azure storage account keys
$secureString = convertto-securestring $storageKey  -asplaintext -force  
$credentialName = "BlobStorageCredential" #give the credential a name - you'll reference it again later (in other scripts, for example)

cd SQLServer:\SQL\$env:COMPUTERNAME

$instances = Get-ChildItem
$instances | new-sqlcredential -Name $credentialName -Identity $storageAccount -Secret $secureString
{{< /highlight >}}