---
title: "Create an Azure Blob Storage Credential for Backup and Restore"
author: "Andrew Bancroft"
date:   2018-01-09
description: "Process for getting a SQL Server database out of SINGLE_USER Mode if you're stuck in it."
type: technical_note
draft: false
comments: true
aliases:
    - /sqlserverscripts/get-out-of-single-user-mode/
---

##### create-credential.ps1
{{< highlight powershell >}}
import-module sqlps

$storageAccount = "<StorageAccountName>"  #replace this with your Azure storage account name
$storageKey = "<StorageAccountKey>"  #replace this with one of your Azure storage account keys
$secureString = convertto-securestring $storageKey  -asplaintext -force  
$credentialName = "BlobStorageCredential" #give the credential a name - you'll reference it again later (in other scripts, for example)

cd SQLServer:\SQL\$env:COMPUTERNAME

$instances = Get-ChildItem
$instances | new-sqlcredential -Name $credentialName -Identity $storageAccount -Secret $secureString
{{< /highlight >}}