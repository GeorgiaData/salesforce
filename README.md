# Salesforce

Upcoming Jan 2021: Add Stay-in-Touch emails: [Contact Update Request by Acuerdo](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B4QhlEAF)
Beforehand, send a message from Mailchimp or Outlook to catch bouncebacks. 
Inform recipents that email will arrive for updating their company profile.  
Include: Contact us if this update email should go to a different recipient.  
  
The following documents our setup for saving Exporter Directory registration in Salesforce.  

## Output as JSON API

[Report - Private](https://na60.salesforce.com/00O0c000009YuiM)  


## Display in Exporter Directory

[Directory - Private](https://georgiadata.github.io/explorer)

<!--
Addition notes reside in the private repo:  
documentation/salesforce  
-->

 


## Associate fields in Lead Object to Account object

[Dolly](dolly.md) can be used to clone fields, but it is not necessary since you still have to manually relate fields after cloning from Account to Lead Object.  

To associate a new field from the Lead object to the Account object, click "Map Lead Files" in the upper right on [Setup > Object Manager > Lead](https://na60.lightning.force.com/lightning/setup/ObjectManager/Lead/FieldsAndRelationships/view).  This is still necessary after running Dolly to copy the field names.  

## Some Fields can NOT be associated, so populate with "Process Builder"

The Account.Description field can not be updated through an associatione.  It does not appear in the dropdown selections. So use Leigh Anna Geraghty's solution here:  
https://success.salesforce.com/answers?id=9063A000000DoY4QAK  

Enter "Processes" in the Quick Find box and choose "Process Builder".
"Set Account Description" instead of "Set Account Type"

Used the following video: Process Builder: Lead Conversion
https://www.youtube.com/watch?v=ceHAqkx7m0I

The "Account Description" field is NOT in alphabetical order, but it's there.  


## Form Assembly Setup

Send lead from Form Assembly to Salesforce Objects - [Tutorial](https://www.formassembly.com/blog/tutorial-quickly-create-a-form-to-populate-any-salesforce-object/)  

To begin:  
	Import > Import from Salesforce  

Form setup:  
    Choose the theme "Copy of Sky"  

To add more fields:  
    Click Connectors (plug icon) > Configure  

Note to Admins: To associate a new field from SalesForce, manually add the field to the FormAssembly form first. Then associate in the Connectors section. For multi-select fields, copy the fetched option list (countries) within the Connectors section and manually paste the field's options list back into the Build page. To load the list for a newly added Salesforce field, click "Go to > Get New Salesforce Objects" in FormAssembly Connections.  

<pre>
NOTE: The current form "help tips" differ slightly following updates from Maxine. 

For Abbey's "Trade Lead" form, we used inspect in the browser in Salesforce to get the Record Type ID.  You can also get it here:
http://www.salesforcegeneral.com/salesforce-articles/salesforce-tip-simple-ways-to-find-record-type-id.html

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

International Sales Contact - "International Sales Point of Contact" Help text: "Please provide name and phone"

Industries Trade

Industries Other - "If your industry is not represented in the options above, please enter additional categories describing your company. Separate multiple categories with commas using up to 255 characters total."

Company Description - "Brief Company Description"

Description of Product or Service - "For display in exporter directory (255 char max)"

Keywords - Help text: "Please provide keywords separated by commas to describe your product(s) and/or service(s)."

GA Exporter - "Are you currently exporting?"

HS Codes - "Comma separated" Text above "Please provide the 6-digit HS code for any products you currently export. Do not use periods or commas to separate digits within each code."

NAICS - "NAICS Industry Codes" - "Comma separated"

Current Export Countries - (Select all that apply)

Target Markets - "Target markets for next 2-3 years (select all that apply)"

International Business Objectives

International Trade Shows - "International trade shows you plan to participate in over the next 2 years"

Domestic Trade Shows - "Domestic trade shows you plan to participate in over the next 2 years"

Lead Time - "How far in advance do you plan for participation in a trade show?"

International Sales Partners - "Are you currently working with any external organizations to support your international sales strategy?"

Comments (first one of two) - "Questions and Comments"

Lead Source (Default to Trade Directory) - hidden

Directories - hidden, default to Exporter Directory


SUBTITLE: Directory Consent

Yes/No - By clicking this box, I acknowledge that I have read and agree to the terms of the GDEcD Privacy Policy.

Yes/No - By clicking this box, I hereby attest that the information that I am submitting is true and correct.




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
Record Type ID - Only used for "Trade Lead" form.
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
</pre>


## Bug Fix for picklist field values sent as one comma separted field

If picklist field values are being submitted as one line containing commas, 
delete and reconnect the fields in the Form Assembly Facebook Connector. 
(Leave them on the frontend form.)  

https://help.formassembly.com/help/348283-field-mapping

Picklist Fields:  

Industries Trade - Restricted last week  
Current Export Countries - Restricted Monday  
Target Markets  
International Business Objectives  
International Sales Partners - "Are you currently working with any external organizations..."  


## Upload

You can add a new export.csv file by dragging it onto this page then click "commit changes":  

https://github.com/GeorgiaData/display/upload/master/products/exporters

Manually adding is temporary until we automate pulling from SalesForce to a static file.  


HOW TO RESTORE PREVIOUS FILES:  

Click "history" on the file's GitHub page:  

https://github.com/GeorgiaData/display/blob/master/products/exporters/export.csv  


Click the <> symbol next to a previous version of the file.  

Navigate to the older version of a file in products/exporters/  

Download the older file and re-upload it to make it the active file.  


When you're looking at the older files, you'll see "tree" in the dropdown.  

Choose "Master" in that dropdown to return to the active files before uploading.  


## Associate Lead to a Queue

(Thus far only used for Trade International Lead)

Trade International Lead - from our international contractors.  

To make a queue: Setup > Users > Queues  

Click new  

Added "Trade International Lead" (Left email and checkbox blank)  

Select Object and Fields > Object Manager > Lead  

Feature Settings > Marketing > Lead Assignment Rules

probably not needed...
Select Role and Subordinate: Trade Director  

Next go to Lead Assignment Rule
Automatically associate sources containing "Trade Intl Office"
Click Web Leads
Lead Source: Trade 
Assign to Queue: Trade International Lead
