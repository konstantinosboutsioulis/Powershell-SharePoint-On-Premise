# Give Persmissions in SharePoint Site

##  Give Persmissions in SharePoint Site with Powershell for SharePoint 2013,2016,2019


Add-PSSnapin Microsoft.Sharepoint.Powershell

Get-SPWeb "https://mydomainexample.com/site_example" | New-SPUser -UserAlias "Domain\Username_or_Group" -PermissionLevel Read
