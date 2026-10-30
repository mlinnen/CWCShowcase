# Annual Event Roll-Over
When preparing for the upcoming year's Showcase of Woodcarvings, administrators must transition data, create the new event entries, copy categories and prizes, update user accounts, and refresh registration assets.

This guide provides a comprehensive checklist and step-by-step instructions for rolling over the application and supporting Google Workspace resources from one competition year to the next.

---

## Roll-Over Checklist

- [ ] **Archive Prior Event Data**: Copy the vendor and carver registration sheets to an archive folder labeled `YYYY Showcase`, and in the copied sheets remove any data that is not the production data for the completed event.
- [ ] **Create New Events**: Create both a **Test** and a **Prod** event entry in the Events module with approved dates.
- [ ] **Record Event IDs**: Note the Event IDs for the previous year and the new test/prod events.
- [ ] **Copy Categories**: Run the Apps Script duplicate function to copy categories from the previous event to the new event.
- [ ] **Update Categories**: Update the new event's categories (including the 7 annual "Best of" categories) and have committee members review.
- [ ] **Copy Prizes**: Run the Apps Script copy function to duplicate prizes from the previous event to the new event.
- [ ] **Update Prizes**: Update prize amounts and awards according to committee decisions and have them reviewed.
- [ ] **Generate Judging Entries**: Run the Apps Script judging generation function to create judging entries from the updated categories.
- [ ] **Assign Prizes**: Associate prizes with the new event's judging entries in Setup Judging.
- [ ] **Review Judging Setup**: Have committee members review judging entries and prize associations.
- [ ] **Update Users**: Deactivate inactive accounts, add new volunteers, verify roles, and assign users to the new event.
- [ ] **Update Google Forms**: Update header images on the Carver and Vendor registration Google Forms.
- [ ] **Update Template Docs**: Update the edition title on the Show Registration template document (e.g., "43rd" to "44th").

---

## 1. Archive & Prepare Google Drive Data

Active registration data sheets are stored in Google Drive under:
`Application/CWC Showcase/data`

1. **Create an Archive Folder**:
   - In Google Drive, create a new folder named `YYYY Showcase` (where `YYYY` is the year of the event just completed).
2. **Archive Vendor Registrations**:
   - Make a copy of the active **Vendor Registrations** spreadsheet (located in `Application/CWC Showcase/data`).
   - Move the copy into the `YYYY Showcase` archive folder.
   - In the **copied** sheet, remove all data that is not for the event (such as test records or erroneous entries), so that it only contains the production data for the event that just completed.
3. **Archive Carver Registrations**:
   - Make a copy of the active **Carver Registrations** spreadsheet (located in `Application/CWC Showcase/data`).
   - Move the copy into the `YYYY Showcase` archive folder.
   - In the **copied** sheet, remove all data that is not for the event (such as test registrations), so that it only contains the production data for the event that just completed.

---

## 2. Create the Next Events (Test and Prod)

You must define two event records in the application: one for testing registration and configuration workflows, and one for the live production event.

### Prerequisites
Before creating the events, obtain the approved schedule from the Show Committee:
- Event Start and End Dates
- Vendor Registration Start and End Dates
- Competitor Registration Start and End Dates (including Early Registration deadline)

### Steps to Create Events
1. From the **Main Menu**, select **Events** > **Events** (see [Events Guide](Events.md)).
2. Click the **Add Icon (+)**.
3. Enter the details for the **Test Event** (e.g., Code: `CWC2027TEST`):
   - Fill in registration and competition dates.
   - Set **Active** to **N** (or **Y** only when actively testing).
4. Click **Save**.
   - *Note: The form closes without a confirmation message.*
5. Click the **Add Icon (+)** again to create the **Production Event** (e.g., Code: `CWC2027`):
   - Fill in official registration and competition dates.
   - Set **Active** to **N** until ready to open for the season.
6. Click **Save**.

### Note the Event IDs
Open the **Detail View** for each event (by clicking its row) and record the following IDs for use in script executions:
- **Previous Year Event ID** (source event to copy from)
- **New Test Event ID**
- **New Prod Event ID**

> [!IMPORTANT]
> Only **1 event** can be active in the system at any given time. Multiple automated triggers and public registration forms rely on the active event record. Do not set the new production event to `Active = Y` until registration is ready to open.

---

## 3. Duplicate and Update Categories

Categories define the division, category numbers, and styles used in the competition. These must be copied from the previous event and updated before judging entries can be created.

### 3.1 Copy Categories via Apps Script
1. Open [Google Apps Script](https://script.google.com/) and log in with an authorized Google account.
2. Select the **CWC Showcase App** project (associated with the *Showcase of Woodcarvings Judging* sheet).
3. Open the `CategoriesTests.gs` file.
4. Locate the `_duplicateCategoryRowsTest()` function.
5. Update the parameters with:
   - The **Previous Event ID** (source)
   - The **New Event ID** (target — run for Test and Prod as needed)
6. In the function dropdown list (next to the **Debug** button), select `_duplicateCategoryRowsTest`.
7. Click **Run** and verify successful completion in the execution log.

### 3.2 Update New Event Categories
1. In the application, navigate to **Categories** > **Categories** (see [Categories Guide](Categories.md)).
2. Review the copied categories against the new year's show guidelines.
3. Update the **7 "Best of" Categories** that change every year:
   - Click the category row to open the **Detail View**.
   - Click the **Pencil Icon** to edit.
   - Update descriptions or criteria as decided by the Show Committee.
   - Click **Save** (no confirmation message will appear).
4. Have at least two Show Committee members review the categories list in the app to confirm accuracy.

---

## 4. Duplicate and Update Prizes

Prizes define the ribbons, monetary awards, and trophies available for the event.

### 4.1 Copy Prizes via Apps Script
1. In the **CWC Showcase App** project on [Google Apps Script](https://script.google.com/), open `PrizesTests.gs`.
2. Locate the `_copyPrizesBetweenEventsTest()` function.
3. Update the parameters with:
   - The **Previous Event ID** (source)
   - The **New Event ID** (target)
4. Select `_copyPrizesBetweenEventsTest` in the function dropdown.
5. Click **Run** and verify execution output.

### 4.2 Update New Event Prizes
1. In the application, navigate to **Prizes** > **Prizes** (see [Prizes Guide](Prizes.md)).
2. Update any prizes according to committee changes:
   - Adjust dollar amounts or award names if changed.
   - Update prizes associated with the 7 "Best of" Categories.
3. Click **Save** to commit any edits.
4. Have committee members review the prize table to ensure amounts, quantities, and descriptions are accurate.

---

## 5. Generate Judging Entries & Assign Prizes

Once categories and prizes are finalized, judging entries are created from the categories, followed by prize assignment.

### 5.1 Generate Judging Entries
1. Follow the procedure outlined in [Create Judging from Categories](Create-Judging-From-Categories.md):
   - In the Apps Script project, open `JudgingTests.gs`.
   - Update `_createJudgingEntriesForEventTest()` with the new Event ID.
   - Select `_createJudgingEntriesForEventTest` and click **Run**.
2. Verify that judging entries appear in **Judging** > **Setup Judging**.

### 5.2 Assign Prizes to Judging Entries
1. Navigate to **Judging** > **Setup Judging** (see [Assigning Prizes](Assign-Prizes.md)).
2. For each category requiring specific awards (such as 1st, 2nd, 3rd place, or Best of):
   - Select the entry row and click the **Pencil Icon**.
   - Assign the appropriate awards in the **1st Place Prize**, **2nd Place Prize**, and **3rd Place Prize** dropdowns.
   - Click **Save**.
3. Have team members review the judging entries to confirm that all prizes are correctly linked.

> [!NOTE]
> Team assignments (Team A, B, C, D) are typically completed closer to the event weekend once judging volunteers are confirmed (see [Assigning Teams](Assign-Teams.md)).

---

## 6. User Management & Volunteer Access

Review accounts and update permissions to ensure only active volunteers have access to the upcoming event.

1. From the **Main Menu**, select **Users** (see [User Management Guide](User-Management.md)).
2. **Deactivate Inactive Users**: Remove or adjust roles for volunteers who are no longer participating.
3. **Add New Users**:
   - Click the **Add Icon (+)** or copy an existing user with similar roles.
   - Enter their **Name**, **Email**, assign appropriate **Roles**, and set the **Event** to the new event.
   - Click **Save**.
4. **Verify Google Accounts & AppSheet Sharing**:
   - Confirm that each user's email is an active Google Account.
   - An administrator must share the AppSheet application with new users directly within the AppSheet Editor.
5. **Assign Users to the New Event**:
   - Ensure continuing volunteers have their default event updated to the new event record.

---

## 7. Update Registration Forms & Document Templates

External registration forms and document templates must be updated with the branding and edition number for the new showcase.

1. **Vendor Registration Google Form**:
   - Open the Vendor Registration Google Form in Google Drive.
   - Update the header banner image with the new showcase year artwork.
   - Review and update dates, fee schedules, or instructions in the form description.
2. **Carver Registration Google Form**:
   - Open the Carver Registration Google Form in Google Drive.
   - Update the header banner image with the new showcase year artwork.
   - Review and update entry fees, deadlines, and rules in the form description.
3. **Show Registration Template Document**:
   - Locate the registration confirmation template Google Doc.
   - Update the title and text to reflect the upcoming edition (e.g., updating "43rd Annual" to "44th Annual Woodcarving Showcase").

---

## 8. Note on Automation & Future Enhancements

Currently, copying categories, duplicating prizes, and generating judging entries require executing test functions in Google Apps Script associated with the *Showcase of Woodcarvings Judging* sheet.

Future enhancements aim to replace manual Apps Script execution with AppSheet bots and action buttons, allowing administrators to initiate category duplication, prize copying, and judging generation directly within the Showcase Application interface.
