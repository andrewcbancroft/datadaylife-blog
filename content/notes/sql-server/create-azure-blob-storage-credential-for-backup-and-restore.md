import-module sqlps

$storageAccount = "<StorageAccountName>"  
$storageKey = "<StorageAccountKey>"  
$secureString = convertto-securestring $storageKey  -asplaintext -force  
$credentialName = "NobleGeneralBlobStorageCredential"

cd SQLServer:\SQL\$env:COMPUTERNAME

$instances = Get-ChildItem
$instances | new-sqlcredential -Name $credentialName -Identity $storageAccount -Secret $secureString
