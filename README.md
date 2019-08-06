# Salesforce

The following documents our set-up for collecting leads.  

## ADD FIELDS TO ACCOUNT FORM

## CLONE FIELDS TO LEAD FORM

The "Dolly Cloning App" by Astrea enables Salesforce admins to clone the standard and custom objects and copies the custom fields of the objects.  

https://astreait.com/dolly_cloning_application/  

Install Dolly (in sandbox first)  
https://appexchange.salesforce.com/listingDetail?listingId=a0N30000000qb65EAA  

After installing, in Salesforce click the 9-box menu icon on the left side.  
Launch the Dolly app and choose the "Clone Fields" tab.  


Type "Account" in the first field.  A list of existing fields will appear.  
Type "Lead" in the second field.  No list will be displayed.  
Select the fields to clone.  

## OUTPUT ACCOUNT FIELDS AS JSON API - Miles using Sandbox

## POPULATE LAT/LON VALUES IF BLANK - Miles

## DISPLAY IN EXPORTER DIRECTORY - Loren


<!--
List of installed packages (in the sandbox)  
https://cs65.lightning.force.com/lightning/setup/ImportedPackage/page?address=%2F0A3&0.source=aloha  

Dolly User Manual  
https://appexchange.salesforce.com/servlet/servlet.FileDownload?file=00P3A00000aoPzZUAU  


Addition notes reside in the private repo:  
documentation/salesforce  



DELETE THIS
Do a view source on the following page and copy the start of the URL (https://dolly.cs65.visual.force.com) from the iFrame.  

https://cs65.lightning.force.com/lightning/n/dolly__Dolly_Home  

https://dolly.cs65.visual.force.com/apex/Homepage?sfdc.tabName=01r0m000000BInU&vfRetURLInSFX=%2Fhome%2Fhome.jsp&ltn_app_id=06m0m000000BxHbAAK&nonce=212c7a02feb11332e3b060c41693eef6654e25c7107a3f713dc09bf09d3f1fdf&sfdcIFrameOrigin=https://cs65.lightning.force.com&tour=&isdtp=p1&sfdcIFrameHost=web&clc=0  

From "Dolly Home" tab  
4. Go to Setup > in Administer > Security Controls > Remote Site Settings  
Or quick search "Remote Site Settings" 
END DELETE THIS
5. Create a New Remote Site Setting > Paste the URL copied above inside Remote Site URL > Save 
-->