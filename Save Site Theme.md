# Save Site Theme

## Save Site Theme using Powershell for Sharepoint 2013 ,2016,2019


$WebURL = "https://mydomain.com/template_url"

#Get the Web Object
$Web= Get-SPWeb $WebURL

#Variables for Save site as template settings
$TemplateName ="Template_Name"
$TemplateTitle ="Template_Title"
$TemplateDescription ="Template_Description"
 
#Option to Save with content
$SaveWithContent= 1  #0 otherwise
 
#Save site as template programmatically with PowerShell
$Web.SaveAsTemplate($TemplateName,$TemplateTitle,$TemplateDescription,$SaveWithContent)


----

