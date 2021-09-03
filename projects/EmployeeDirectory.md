---
layout: project
type: project
image: images/employeeDir.PNG
title: EmployeeDirectory
permalink: projects/employeeDirectory
# All dates must be YYYY-MM-DD format!
date: 2021-09-02
labels:
  - Sharepoint List
  - Directory
summary: Boss wanted an employee directory by the end of the day.
---

<img class="ui image" src="{{ site.baseurl }}/images/employeeDir.PNG">

Using several csv files taken from Verizon, TMobile, HDT and Activer Directoy I was able to combine them into a single sheet.
Then figuring out the colisions assign each user with a set of attributes "Title","Email","Department" etc..

Then assigning these objects properites to a sharepoint list
```ps1
foreach ($Record in $import){
    Write-Host "updating the List for" $Record.'First Name'
    Add-PnPListItem -List "All" -Values @{
    "Title" = $Record.'Display Name';
    "Email" = $Record.'Primary Email';
    "SecondaryEmail" = $Record.'Alternate Email';
    "JobTitle" = $Record. 'Job Title';
    "Department" = $Record.'Department';
    "PhoneNumber" = $Record.'Phone';
    "Location" = $Record.'Location'
    }
}
```

This scrip sits on a server and is run once a week to update the list from a master csv. The bulk of the work for this project was gathering all of the necessary information deciding what was updated and what wasn’t to create the unified list.

An issue I encountered on this was that when an item gets deleted, SharePoint will not remove that entry simply empty it and hide it from view. This causes a problem when the list is updated, instead of starting at 1 it will start at end of the previous list. The new updated list will have an id number of 700 instead of 1. With each subsequent update the starting id number will increase. I checked and sharepoint id’s cap is around a million or so. This means that over time the directory will break in around five years if the updates hold to a weekly schedule. 


Code: [https://github.com/hbzxc/EmployeeDirectory](https://github.com/hbzxc/EmployeeDirectory)

