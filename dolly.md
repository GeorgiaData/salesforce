# Dolly App

## Copy Fields from Account to Lead Object using Dolly

Add Fields to Account Form then Clone Fields to Lead Form. This is helpful if you are moving a lot of fields.  For only a few, it's easier to do manually.  

The "Dolly Cloning App" by Astrea enables Salesforce admins to clone the standard and custom objects and copies the custom fields of the objects.  
<!--
List of installed packages (in the sandbox)  
https://cs65.lightning.force.com/lightning/setup/ImportedPackage/page?address=%2F0A3&0.source=aloha  

Dolly User Manual  
https://appexchange.salesforce.com/servlet/servlet.FileDownload?file=00P3A00000aoPzZUAU 
-->
https://astreait.com/dolly_cloning_application/  

<span style="border:1px solid #ccc">
The following may not be necessary:

Install Dolly (in sandbox first)  
https://appexchange.salesforce.com/listingDetail?listingId=a0N30000000qb65EAA  

After installing, to go to the app in Salesforce, click the 9-box menu icon on the left side. 

The Dolly app home page says to go to  "Setup > Remote Site Settings"

Do a view source to get a domain from the iFrame that contains Dolly, similar to the following: 
https://dolly.ap2.visual.force.com/
</span>

In the Dolly app (9-box menu) choose the "Clone Fields" tab.  
Type "Account" in the first field and choose auto-complete.  A list of existing fields will appear.  
Type "Lead" in the second field and choose auto-complete.  No list will be displayed.  
Select the fields to clone.  

Set the Field Level Settings to make the new fields visible on layout. 
Go to settings and search for "Field Accessibility" (A subset of Security).

Fields appeared here:

https://na60.lightning.force.com/lightning/setup/ObjectManager/Lead/FieldsAndRelationships/view
(This may have been delayed)

Choose the field, 
Click "hidden" in first column (Master) for Trade row.

Click the two "visible" checkboxes for each field. (Or maybe only "Trade" is needed.)

Do this for both "Trade" and "GDEcD Trade Admin" (second one will already have 1 box checked)

Check "Visible" at top and save.

Drag the new fields onto the layout. 
