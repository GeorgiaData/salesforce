# Salesforce

The following documents our setup for collecting leads. Collecting leads externally allows the state to avoid the $5 per user per month fee that applies to contacts that self-register using Saleforce communities.  


## Add Fields in Salesforce

Add Fields to Account Form then Clone Fields to Lead Form

The "Dolly Cloning App" by Astrea enables Salesforce admins to clone the standard and custom objects and copies the custom fields of the objects.  
<!--
List of installed packages (in the sandbox)  
https://cs65.lightning.force.com/lightning/setup/ImportedPackage/page?address=%2F0A3&0.source=aloha  

Dolly User Manual  
https://appexchange.salesforce.com/servlet/servlet.FileDownload?file=00P3A00000aoPzZUAU 
-->
https://astreait.com/dolly_cloning_application/  

Install Dolly (in sandbox first)  
https://appexchange.salesforce.com/listingDetail?listingId=a0N30000000qb65EAA  

After installing, in Salesforce click the 9-box menu icon on the left side. 

Important, as stated on the Dolly app home page, go to:  
Setup > "Remote Site Settings"

Do a view source to get a domain from the iFrame that contains Dolly, similar to the following: 
https://dolly.ap2.visual.force.com/

Not sure if the above actually works, but do it first. 
Didn't do first time.

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


## Form Assembly Setup

Send lead from Form Assembly to Salesforce Objects
https://www.formassembly.com/blog/tutorial-quickly-create-a-form-to-populate-any-salesforce-object/

To begin:
	Import > Import from Salesforce

Form setup:
    Choose the theme "Copy of Sky"

To add more fields:
    Click Connectors (plug icon) > Configure
    

EXPORTER FORM
Retain these from Lead. Require first 12, except mobile phone.

SUBTITLE: Your Contact Information
Title
First Name
Last Name
Phone
Mobile Phone (hidden)
Email

SUBTITLE: Company Information
Company
Website
Street
City
State/Province
Zip/Postal Code

Total GA Employment - "Total Number of Employees in Georgia"
Employees - "Total Number of Employees Worldwide"

International Sales Contact - "International Sales Contact Point of Contact" Help text: "Please provide name and phone"

Industries Trade

Company Description - Becomes Brief Company Description

Description of Product or Service - "For display in exporter directory (255 char max)"

Keywords - Help text: "Please provide keywords separated by commas to describe your product(s) and/or service(s)."

GA Exporter - "Are you currently exporting?"

HS Code - "Comma separated" Text above "Please provide the 6-digit HS code for any products you currently export. Do not use periods or commas to separate digits."

NAICS - "Comma separated"
Current Export Countries (Select all that apply)

Target Markets - "Target markets for next 2-3 years (select all that apply)"

International Business Objectives
International Trade Shows - "International trade shows you plan to participate in over the next 2 years"
Domestic Trade Shows - "Domestic trade shows you plan to participate in over the next 2 years"
Lead Time - "How far in advance do you plan for participation in a trade show?"

International Sales Partners - "Are you currently working with any external organizations to support your international sales strategy?"

Comments (first one of two) - "Comments, Questions and Feedback"


SUBTITLE: Directory Consent

Yes/No - By clicking this box, I acknowledge that I have read and agree to the terms of the GDEcD Privacy Policy.

Yes/No - By clicking this box, I hereby attest that the information that I am submitting is true and correct.

Lead Source (Default to Trade Directory) - hidden



NOT USED

Annual Revenue
Appointment Perference
Comments (dup)
Company Applying for Cert
Company Size
Converted
Correlation Data
CorrelationID
Country
Data.com Key
Description
Directories
Directory Consent
Email Bounced Date
Email Bounced Reason
Fax
Geocode Accuracy
Georgia Made Employees
Georgia Made Products
Goals for Market
Industry
Information On
Interested In
Key Issues
Latitude
Latitude (MapAnything)
Lead ID
Lead Source Details
Longitude
Longitude (MapAnything)
MC Subscriber
Organization Type
Owner ID
Partner in Market
PercentageSalesExported
Percent product/solution
Rating
Record Type ID
Regions
Salutation
Status
Team
Top 3 Market Preference
Type of Operation
Unique produce description
Web Source
competitive advantage
opentext

## Output as JSON API


## Populate Lat/Lon Values


## Display in Exporter Directory

[Directory - Private](https://georgiadata.github.io/explorer)

<!--
Addition notes reside in the private repo:  
documentation/salesforce  
-->