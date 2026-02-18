# Create Judging from Categories
When you are preparing for the next event it is escential to make sure all the categories for the event are setup correctly, because they are used to generate all the judging entries.

This currently is a manual process that should only be performed by an administrator.  It assumes that no judging entries currently exist for the given event.  It also assumes that you have a valid list of catagories for the event.  

What you need befor generating the list of judging entries:
1. The Event Code that you want to generate the judging entries for.
    1. Open the Showcase Application
    1. Select Events from the main menu
    1. Click on the event you want to generate the data for
    1. Copy the Event ID from the detail view
1. Access to the App Script that is associated to the Judging Google Sheet.
1. If the event already has juding data then you will need to delte the data first
1. If the event does not have any judging data then you can generate the data 

## 1. When to do this
You will only want to execute this process before the judging has started and give yourself enough time to re-enter the Team Assignments as well as the Prize Assignments.  This basically deletes all your judging data and re-creates it from the categories. The best time to do this is after your categories have been finalized and at least 3 weeks before the event to give the Judging Manager enough time to make the Team Assignments. 

If you only need to make a few changes then use the [Setup Judging](Setup-Judging.md) functionality to make simple edits, delete invalid entries or add new entries.

## 2. Backup data
As an extra layer of safty you can make a copy of the **Showcase of Woodcarvings Judging** sheet in the **Applications/CWC Showcase/data** folder on Google Drive.

Another option you can do that isn't really a good way to restore data but does allow you to have some limited copy of your specific event for things like remembering Team Assignment or remebering Prize assignments.  You do an Judging Export shich emails you the judging entries for a given envet.

## 3. Accessing the AppsScript project
1. Go to https://script.google.com/
1. Log into a google account that has access to the script project
1. Select the **CWC Showcase App** project
1. Select the JudgingTests.gs script 

## 4. Delete Judging Data 
A function exists that allows you to delete all judging entries for a given Event ID.  This will also remove all Team and Prize assignments to the judging entries.
1. Edit the _deleteJudgingEntriesForEventTest to pass in the Event ID you want to delete the data for
1. Make sure the Function to Run drop down (next to the debug menu) has the _deleteJudgingEntriesForEventTest selected
1. Click the run button
1. Verify the data was deleted

## 3. Generate Judging Data
This screen allows you to define which categories and styles are ready for judging and which teams are assigned to them.
1. Edit the _createJudgingEntriesForEventTest to pass in the Event ID you want to create the data for
1. Make sure the Function to Run drop down (next to the debug menu) has the _createJudgingEntriesForEventTest selected
1. Click the run button
1. Verify the data was created

## 4. Re-assgin Data
After the judging entries are re-generated you will have to [re-assign teams](Assign-Teams.md).  You will also need to [re-assign prizes](Assign-Prizes.md).
