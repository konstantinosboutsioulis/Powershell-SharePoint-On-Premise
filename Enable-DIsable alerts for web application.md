##How to enable or disable alerts for web application in SharePoint 2013,2016,2019

#How to enable or disable alerts for web application in SharePoint 2013,2016,2019 using Powershell


## To enable alerts for Web application
 
$SPwebapp=Get-SPWebApplication "http://SharePointSite.com"

$SPwebapp.AlertsEnabled = $true #$false to Dissable 

$SPwebapp.Update()
 
