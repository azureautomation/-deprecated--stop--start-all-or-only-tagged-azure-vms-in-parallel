(Deprecated) Stop / Start all or only tagged Azure VMs in parallel
==================================================================

            

**Updated at 05/17/2019 : This runbook is deprecated. You should use the new Az Powershell module by using [this runbook to stop / start VMs in parallel](https://gallery.technet.microsoft.com/scriptcenter/Stop-Start-all-or-only-8a7e11a2?redir=0) or [this runbook to stop /start VMs in sequence](https://gallery.technet.microsoft.com/scriptcenter/Az-Stop-Start-all-or-only-8a8fcab4?redir=0). **


**[See more about the new **Az PowerShell module for Azure**](https://docs.microsoft.com/en-us/powershell/azure/new-azureps-module-az?view=azps-2.0.0)**


 


**DESCRIPTION**


This PowerShell Workflow Runbook connects to Azure using an Automation Run As account, retrieves the power status of Azure V2 VMs and turns off / on  in parallel those that are turned on / off. You can attach a recurring schedule to this runbook to
 run it at a specific time.


**REQUIRED**


1. An Automation connection asset called AzureRunAsConnection that contains the information for connecting with Azure using a service principal.  To use an asset with a different name you can pass the asset name as a input parameter to this runbook.


2. An Action input parameter value that allows runbook to handle Azure V2 power state. The parameter must be set to 'Stop' or 'Start'.


3. Ensure all needed AzureRm modules match the required versions (6.1.1+ for AzureRm.Automation, 5.9.1+ for AzureRm.Compute, 5.8.3+ for AzureRm.Profile and 6.7.3+ for AzureRm.Resources). Please use
[this method](https://github.com/Microsoft/AzureAutomation-Account-Modules-Update) to update your modules.


**OPTIONAL**


3. A TagName input parameter value that allows scoping the V2 VMs to only tagged VMs.


4. A TagValue input parameter value that allows scoping the V2 VMs to a particular tag value.


**AUTHOR**


Farouk FRIHA


**LAST EDIT**


2019-11-06


**RELEASE NOTES**


2016-11-30 First release


2016-12-03 Handle changes to parameters


2019-17-05 Replaced Find-AzureRmResource with Get-AzureRmResource


2019-11-06 Added details regarding PowerShell modules versions


**RUNBOOK CONTENT**


** **

** **




        
    
TechNet gallery is retiring! This script was migrated from TechNet script center to GitHub by Microsoft Azure Automation product group. All the Script Center fields like Rating, RatingCount and DownloadCount have been carried over to Github as-is for the migrated scripts only. Note : The Script Center fields will not be applicable for the new repositories created in Github & hence those fields will not show up for new Github repositories.
