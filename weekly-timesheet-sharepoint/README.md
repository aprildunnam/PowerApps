# Power Apps Weekly Timesheet Template

## Summary

This sample shows how to implement a weekly timesheet application using Power Apps (canvas app).

![picture of the sample](assets/timecardEntry.png)

## Applies to

![Power Apps](https://img.shields.io/badge/Power%20Apps-Yes-green "Yes")
![Power Automate](https://img.shields.io/badge/Power%20Automate-No-red "No")
![Power BI](https://img.shields.io/badge/Power%20BI-No-red "No")
![Power Pages](https://img.shields.io/badge/Power%20Pages-No-red "No")
![Power Virtual Agents](https://img.shields.io/badge/Power%20Virtual%20Agents-No-red "No")
![Dataverse](https://img.shields.io/badge/Dataverse-No-red "No")
![AI Builder](https://img.shields.io/badge/AI%20Builder-No-red "No")
![Custom Connectors](https://img.shields.io/badge/Custom%20Connectors-No-red "No")
![Power Fx](https://img.shields.io/badge/Power%20Fx-No-red "No")

## Compatibility

![Premium License](https://img.shields.io/badge/Experimental%20Features-No-green.svg "Premium Power Apps license not required")
![Experimental Features](https://img.shields.io/badge/Experimental%20Features-No-green.svg "Does not rely on experimental features")

## Contributors

- [April Dunnam](https://github.com/aprildunnam)

## Version history

Version|Date|Comments
-------|----|--------
1.0|January 08, 2024 |Initial release

## Features

This sample illustrates how to implement a weekly timesheet application using Power Apps.  The solution consists of a canvas app and utilizes modern controls, named formulas and containers. 

### Key Features of the solution include:
* The ability to submit time cards in a weekly view
![SubmitTimeCard](assets/timecardEntry.png)
* View all submitted time cards and their status as an employee
![MyTimeCards](assets/myTimeCards.png)
* Have a manager view to see your team's time cards and approve
* The sample uses SharePoint as the back end so no additional license is required but can be easily adapted to use Dataverse


## Data Sources

* SharePoint

## Step 1: Setup the lists
The first list is **BillTo**, which is a reference list to store what to assign the time to.  This is customizable to whatever you want to assign the time to. For example, this can be to a particular customer, a project, or to a type of time (overtime, regular, etc). 

| **List Column** | **Data Type** | **Notes** |
| --- | --- | --- |
| Title |Single line of text |Default column, used for BillTo name |


The second list is **TimeEntries** which is the main list that stores all of the timesheet data.

| **List Column** | **Data Type** | **Notes** |
| --- | --- | --- |
| Title |Single line of text |Default column, used for project name |
| Comments |Multiple lines of text | |
| Manager Comments |Multiple lines of text | |
| EmployeeTxt |Single lines of text | |
| Status |Choice |Values: Pending, Submitted for Approval, Approved, Rejected |
| Week Start |Date | |
| Employee |Person or Group | |
| Manager |Person or Group | |
| Mon |Number | |
| Tues |Number | |
| Weds |Number | |
| Thurs |Number | |
| Fri |Number | |
| Sat |Number | |
| Sun |Number | |
| Total |Number | |
| BillTo |Lookup | BillTo List, Title Column|

## Installation

* [Download](./solution/WeeklyTimesheetTemplateSP_1_0_0_2.zip) the `.zip` from the `solution` folder
* Within **Power Apps Studio**, import the solution `.zip` file using **Solutions** > **Import Solution** and select the `.zip` file you just packed.
* Open the Timesheet Template app in Edit mode
* Go to the datasources tab and remove the BillTo and TimeEntries tables
![MyTimeCards](assets/deleteBillTO.png)
![MyTimeCards](assets/deleteTimeEntries.png)
* In the datasources tab, click add new and search for SharePoint
![AddData](assets/addSP.png)
* Navigate to where you created the lists and add the TimeEntries and BillTo list to your app
![AddData](assets/addSPLists.png)
* Save and Publish


## Disclaimer

**THIS CODE IS PROVIDED *AS IS* WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESS OR IMPLIED, INCLUDING ANY IMPLIED WARRANTIES OF FITNESS FOR A PARTICULAR PURPOSE, MERCHANTABILITY, OR NON-INFRINGEMENT.**

## For more information

* [Overview of creating apps in Power Apps](https://docs.microsoft.com/powerapps/maker/)
* [Power Apps canvas apps documentation](https://docs.microsoft.com/powerapps/maker/canvas-apps/)

<img src="https://m365-visitor-stats.azurewebsites.net/powerplatform-samples/samples/readme-template" />

---