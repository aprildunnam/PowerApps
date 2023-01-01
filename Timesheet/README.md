
# Weekly Timesheet Power App Template

## Summary

This timesheet application is a tablet-based canvas app that gives you a way to create and manage weekly timesheets.

### Home Screen

![home screen](./timesheet.png)  

### Timesheet Entry Screen

![timesheet entry screen](./timesheet.png)  


## Applies to

* [Microsoft Power Apps](https://docs.microsoft.com/powerapps/)

## Compatibility

![Power Apps Source File Pack and Unpack Utility 0.20](https://img.shields.io/badge/Packing%20Tool-0.20-green.svg)
![Premium License](https://img.shields.io/badge/Premium%20License-Not%20Required-green.svg "Premium Power Apps license not required")
![Experimental Features](https://img.shields.io/badge/Experimental%20Features-No-green.svg "Does not rely on experimental features")
![On-Premises Connectors](https://img.shields.io/badge/On--Premises%20Connectors-No-green.svg "Does not use on-premise connectors")
![Custom Connectors](https://img.shields.io/badge/Custom%20Connectors-Not%20Required-green.svg "Does not use custom connectors")

## Authors

Solution|Author(s)
--------|---------
Timesheet Power App | [April Dunnam](https://github.com/aprildunnam) ([@aprildunnam](https://www.twitter.com/aprildunnam) )

## Version history

Version|Date|Comments
-------|----|--------
1.0|February 16, 2021|Initial release


## Features

This sample illustrates the following concepts:

* Creating an appealing home screen for your applications
* Creating a timesheet application that you can use for your production needs

## Prerequisites

You'll need to make sure to update the data sources (see below)

## Data Sources
 
This app uses SharePoint as a data source and requires two SharePoint Lists with the following fields:

### BillTo List

This list contains the lookup data to associate a timesheet entry with a job or client to bill to.  Set the list up as follows:

|Type|Internal Name|Required|
|---|---|:---:|
|Single line of text|Title|Yes|

### TimeEntries List

This list contains the timesheet entries.  Set the list up as follows:

|Type|Internal Name|Required|
|---|---|:---:|
|Single line of text|Title|Yes|
|Number|Mon|No|
|Number|Tues|No|
|Number|Weds|No|
|Number|Thurs|No|
|Number|Fri|No|
|Number|Sat|No|
|Number|Sun|No|
|Multi line of text|Comments|No|
|Choice|Status|No|
|Person or Group|Employee|No|
|Person or Group|Manager|No|
|Lookup|BillTo|No|
|Date|WeekStart|No|
|Number|Total|No|

## Minimal Path to Awesome

* [Download](https://github.com/pnp/powerapps-samples/blob/main/samples/Timesheet/solution/WeeklyTimesheet.msapp) the `.msapp` from the `solution` folder
* Use the `.msapp` file using **File** > **Open** > **Browse** within Power Apps Studio.
* Select the **Data** tab
* Remove the `BillTo` and `TimesheetEntries` data sources from the app
* Add new data sources for the `BillTo` and `TimesheetEntries` SharePoint Lists you created in your environment
* Save and Publish

## Using the Source Code

You can also use the [Power Apps CLI](https://docs.microsoft.com/powerapps/developer/data-platform/powerapps-cli) to pack the source code by following these steps::

* Clone the repository to a local drive
* Pack the source files back into `.msapp` file:
  ```bash
  pac canvas pack --sources pathtosourcefolder --msapp pathtomsapp
  ```
  Making sure to replace `pathtosourcefolder` to point to the path to this sample's `sourcecode` folder, and `pathtomsapp` to point to the path of this solution's `.msapp` file (located under the `solution` folder)
* Use the `.msapp` file using **File** > **Open** > **Browse** in Power Apps Studio.
