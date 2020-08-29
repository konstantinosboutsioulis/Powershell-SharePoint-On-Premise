# Break Inheritance

## Break site inheritance Permissions using Powershell for Sharepoint 2013 ,2016,2019




Add-PSSnapin Microsoft.Sharepoint.Powershell

$webURL = "https://mydomainexample.com/site_example"

$web = Get-SPWeb $webURL

$web.BreakRoleInheritance($true)
