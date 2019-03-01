# Audits all Resource Groups that do not have a specific Tag count

Audits all Resource Groups that do not have a specific Tag count.
Within this Policy, you sepcify the Tag Count Value that will be used for identifying the Resource Groups Tags requirment.

## Try in the Azure Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-policy%2Fmaster%2Fsamples%2FResourceGroup%2Faudit-resourceGroup-without-tag-count%2Fazurepolicy.json)

## Try with PowerShell

````powershell
$definition = New-AzPolicyDefinition -Name "audit-resourceGroup-without-tag-count" -DisplayName "Audit Resource Groups based on Tag count" -description "Audits all Resource Groups that do not have a specific Tag count." -Policy 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/ResourceGroup/audit-resourceGroup-without-tag-count/azurepolicy.rules.json' -Parameter 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/ResourceGroup/audit-resourceGroup-without-tag-count/azurepolicy.parameters.json' -Mode All
$definition
$assignment = New-AzPolicyAssignment -Name <assignmentname> -Scope <scope> -tagName <tagName> -tagValue <tagValue> -PolicyDefinition $definition
$assignment 
````

## Try with CLI

````cli
az policy definition create --name 'audit-resourceGroup-without-tag-count' --display-name 'Audit Resource Groups based on Tag count' --description 'Audits all Resource Groups that do not have a specific Tag count.' --rules 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/ResourceGroup/audit-resourceGroup-without-tag-count/azurepolicy.rules.json' --params 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/ResourceGroup/audit-resourceGroup-without-tag-count/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "audit-resourceGroup-without-tag-count" 
````