# Install AzureAD module

`Install-Module -Name AzureAD`

## To test

`Connect-AzureAD`

# Connect with crednetials

$cred = Get-Credential

*Enter office 365 user login details to check connection*

`Connect-AzureAD -Credential $cred`

## Disconnect
`Disconnect-AzureAD`

# Connecting to SharePoint Online

## Get Credentials

`$cred = get-credential`

## Establish Connection

`Connect-SPOService -Url https://contoso-admin.sharepoint.com -credential $cred / -UseWebLogin` 

## Disconnect
`Disconnect-SPOService`


# Install SharePoint Pattern and Practices PowerShell Cmdlets

`Install-Module -Name SharePointPnPPowerShellOnline` 

## Connect to SharePoint Online

`Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -Credential $cred`

## Disconnect 
`Disconnect-PnpOnline`

# Connect to Exchange online

## Get Connection String
$cred = Get-Credential

## Establish connection
$session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRirection

## Add remote session into current session
import-PSSession $session

## Test
`Get-Command -Module $moduleName`

`Get-DistributionGroup`

# Connect to Security and Compliance Admin

`$cred = Get-Credential`

`$session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection`


# Connect to Skype for Business

`Install Skype for business PowerShell Module online`

## Establish connection

`$session = New-CsOnlineSession -Credential $cred`

## Import session

`Import-PSSession $session`

*P.S. For Command not found issue import module manually from the local installed location*

# Connect to Microsoft Teams

`Install-Module -Name MicrosoftTeams`

`Cocnnect-MicrosoftTeams $cred`
