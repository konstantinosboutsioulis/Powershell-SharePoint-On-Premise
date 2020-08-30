##  Create Delete Alerts for SharePoint Library
#  Create Delete Alerts for SharePoint Library using Powershell in Sharepoint 2013,2016,2019


# Create a New alert for a user 

$SPsite = Get-SPSite "https://mydomainexample.com/site_example"

$SPweb=$SPsite.Rootweb

$SPlist=$SPweb.lists["List Name"]

$SPuser = $SPweb.EnsureUser('Domain\user')

$SPnewAlert = $SPuser.Alerts.Add()

$SPnewAlert.Title = "Test Alert"

$SPnewAlert.AlertType=[Microsoft.SharePoint.SPAlertType]::List

$SPnewAlert.List = $SPlist

$SPnewAlert.DeliveryChannels = [Microsoft.SharePoint.SPAlertDeliveryChannels]::Email

$SPnewAlert.EventType = [Microsoft.SharePoint.SPEventType]::Add

$SPnewAlert.AlertFrequency = [Microsoft.SharePoint.SPAlertFrequency]::Immediate

$SPnewAlert.Update()

$SPweb.Dispose()

$SPSite.Dispose()


# Create a New alert for Group
 
$SPweb = Get-SPWeb "https://mydomainexample.com/site_example"

$SPgroup = $SPweb.Groups["Group Name"]

$SPlist = $SPweb.Lists["List Name"]

foreach ($SPuser in $SPgroup.Users){

     $alert = $SPuser.Alerts.Add()
     
     $alert.Title = "Test Alert"
     
     $alert.AlertType = [Microsoft.SharePoint.SPAlertType]::List
     
     $alert.List = $SPlist
     
     $alert.DeliveryChannels = [Microsoft.SharePoint.SPAlertDeliveryChannels]::Email
     
     $alert.EventType = [Microsoft.SharePoint.SPEventType]::Add
     
     $alert.AlertFrequency = [Microsoft.SharePoint.SPAlertFrequency]::Immediate
     
     $alert.Update()
     
}

$SPweb.Dispose()


