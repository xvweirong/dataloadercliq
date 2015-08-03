# Prerequisites #
Please complete the instructions on [UsingCLIq](UsingCLIq.md) before the instructions on this page.

# Instructions #
  1. Replace _processname_/read/_processname_.csv with your source CSV file.
```
"ID","LASTNAME","EMAIL","COMPANY"
"00Q7000000TNtBCEA1","Miller","nouser@acme.com","Acme"
"00Q7000000TNtBDEA1","Smith","noone@widgetmaker.com","Widgets R US"
```
    * Do not change the file name.  Just replace the existing .CSV file with your file.
    * Note the headers for each column.
  1. Open _processname_/config/_processname_.sdl.  Create a mapping with the CSV column header on the left and the Salesforce Field on the right.
```
# Created by Dataloader Cliq
#
# Create your field mapping list in the following format
ID=Id
LASTNAME=LastName
EMAIL=Email
COMPANY=Company
```
    * **The Salesforce Field is case-sensitive**
    * Insert should not have an "Id" mapping
    * Update requires an "Id" mapping
    * Delete only needs an "Id" mapping

See https://na1.salesforce.com/help/doc/en/loader_columns.htm for more details.