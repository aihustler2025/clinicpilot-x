# Assistant QA: Leads Module Step 2A

Updated: 2026-05-26

## Purpose

Test the ClinicPilot X Leads module after Step 2A. Follow the steps exactly and record anything that does not match the expected result.

## Test URL

Open:

`https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app/leads`

Sign in with the admin account if asked. Do not share or record the password.

## Test Data

Use these exact test leads.

### Lead 1

Full name:

`Sarah Johnson`

Email:

`donjericho617+sarahjohnson@gmail.com`

Phone:

`+1 555 010 1001`

Source:

`Manual`

Source detail:

`manual-assistant-test`

Service:

`Botox consultation`

Original message:

`I would like pricing and availability for a Botox appointment this week.`

Internal notes:

`Assistant QA test lead.`

Consent:

Checked

### Lead 2

Full name:

`Michael Chen`

Email:

`donjericho617+michaelchen@gmail.com`

Phone:

`+1 555 010 1002`

Source:

`Website`

Source detail:

`contact-form-demo-site`

Service:

`Dental implant consultation`

Original message:

`I want to know the cost range and financing options for dental implants.`

Internal notes:

`Assistant QA website-source lead.`

Consent:

Checked

### Lead 3

Full name:

`Vendor Test`

Email:

`donjericho617+vendor1@gmail.com`

Phone:

`+1 555 010 1003`

Source:

`Email`

Source detail:

`inbox-vendor-test`

Service:

`Not applicable`

Original message:

`We sell marketing lists and want to pitch your clinic.`

Internal notes:

`Assistant QA vendor/solicitation style lead.`

Consent:

Unchecked

## Part 1: Page Loads

1. Open the Leads page.
2. Confirm the page title says `Leads`.
3. Confirm there is an `Add lead` button.
4. Confirm there is no `Demo data` badge on the Leads page.
5. Confirm the search box says `Search by name, email, phone, or service...`.
6. Confirm there are two filters:
   - `All statuses`
   - `All sources`

Expected result:

The Leads page loads without errors and shows real-data controls.

## Part 2: Add Lead

Repeat this section for Lead 1, Lead 2, and Lead 3.

1. Click `Add lead`.
2. Fill in Full name.
3. Fill in Email.
4. Fill in Phone.
5. Fill in Service of interest.
6. Select Source.
7. Fill in Source detail.
8. Leave Status as `New`.
9. Fill in Original message.
10. Fill in Internal notes.
11. Check or uncheck Consent based on the test data.
12. Click `Create lead`.

Expected result:

- A success message appears.
- The lead appears in the table.
- The Loaded count increases.
- The New count increases unless you later change the status.

## Part 3: Refresh Persistence

1. Refresh the browser page.
2. Confirm all created leads are still visible.

Expected result:

The leads remain visible after refresh.

## Part 4: Search

1. Search `Sarah`.
2. Confirm only Sarah Johnson appears.
3. Clear search.
4. Search `Michael`.
5. Confirm only Michael Chen appears.
6. Clear search.
7. Search `dental`.
8. Confirm Michael Chen appears because service includes dental implant consultation.
9. Clear search.

Expected result:

Search filters by name, email, phone, or service.

## Part 5: Status Filter

1. Open `All statuses`.
2. Select `New`.
3. Confirm the visible list only shows New leads.
4. Select `All statuses` again.

Expected result:

Status filter narrows the list and can be cleared.

## Part 6: Source Filter

1. Open `All sources`.
2. Select `Manual`.
3. Confirm Sarah Johnson appears.
4. Select `Website`.
5. Confirm Michael Chen appears.
6. Select `Email`.
7. Confirm Vendor Test appears.
8. Select `All sources` again.

Expected result:

Source filter narrows the list and can be cleared.

## Part 7: Edit Lead

Use Sarah Johnson.

1. Click Sarah Johnson's `Edit lead` button.
2. Change Status from `New` to `Contacted`.
3. Change Internal notes to:

`Assistant changed status to Contacted.`

4. Click `Save changes`.
5. Confirm Sarah Johnson now shows status `Contacted`.
6. Refresh the page.
7. Confirm Sarah Johnson is still `Contacted`.

Expected result:

Edited status and notes persist after refresh.

## Part 8: Review Queue

1. Open:

`https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app/leads?filter=review`

2. Confirm a banner says the review queue is showing.
3. Confirm status filter is set to `New`.
4. Confirm Sarah Johnson does not show if she was changed to `Contacted`.
5. Confirm New leads still appear.
6. Click `Clear filter`.

Expected result:

Review queue shows New leads and can be cleared.

## Part 9: Dashboard Buttons

Open:

`https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app/`

1. Confirm Quick Actions show:
   - Add Lead
   - New Appointment
   - Send Test Notification
   - Open Review Queue
2. Confirm these are not shown:
   - Start AI Call
   - Send SMS
   - Payment Link
3. Click `Send Test Notification`.
4. Confirm a local test notification appears and says no external messages are sent.
5. Click `Open Review Queue`.
6. Confirm it opens `/leads?filter=review`.

Expected result:

Dashboard actions are honest and do not trigger paid/external integrations.

## Known Issue To Watch

After creating a lead, the Created column may show a strange time such as `about 8 hours ago` even though the lead was just created.

If this happens, record it as:

`Created timestamp/timezone display issue`

## Bug Report Format

Use this format for every problem:

```text
Module: Leads
Step:
Expected:
Actual:
Screenshot:
Severity: Critical / High / Medium / Low
Notes:
```

## Pass Criteria

The Leads module passes if:

- Leads can be created.
- Leads remain after refresh.
- Search works.
- Status filter works.
- Source filter works.
- Edit status/notes works.
- Review queue works.
- Dashboard buttons are correct.
- No external/paid integrations are triggered.

