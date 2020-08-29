# Create Site From Theme

## Create New Site From Theme using Powershell for Sharepoint 2013 ,2016,2019




Add-PSSnapin Microsoft.Sharepoint.Powershell
$web = get-spweb https://mydomainexample.com/template_url
$template = $web.GetAvailableWebTemplates(1033) | Where-Object {$_.Title -eq "Template_Name"}
$newweb = New-SPWeb -Url "https://mydomainexample.com/new_site_url" -Name "Name for my site"
$newweb.ApplyWebTemplate($template.Name)
