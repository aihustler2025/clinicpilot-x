# ClinicPilot X Assistant Dashboard QA Checklist

Updated: 2026-05-25

## Purpose

Use this checklist to test the ClinicPilot X Dashboard preview in a repeatable way. Record every issue with the page/module name, exact action, expected result, actual result, screenshot, and time.

## Test Accounts

Admin:

- Email: `donjericho617@gmail.com`
- Password: owner-controlled password created during signup.

Staff test account:

- Use a plus-address such as `donjericho617+staff1@gmail.com`.
- Password should be created and controlled by the owner.

Do not send passwords in chat or screenshots.

## Login URLs

- App preview: `https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app/`
- Login page: `https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app/auth`

## Admin Smoke Test

1. Open the login page.
2. Sign in as `donjericho617@gmail.com`.
3. Confirm the app loads the dashboard instead of `/unauthorized`.
4. Confirm the sidebar shows the expected modules.
5. Open each module and note whether it loads without a blank page or error:
   - Dashboard
   - Calendar
   - Appointments
   - Leads
   - Patients
   - Staff
   - Automation Center
   - Voice Assistant
   - Payments
   - Integrations
   - Settings
6. Open the top-right profile menu.
7. Confirm these menu items appear:
   - Profile
   - Settings
   - Support
   - Logout
8. Click Logout and confirm it returns to `/auth`.

## Staff Role Test

1. Sign out from the admin account.
2. Sign in as a staff-only test account.
3. Confirm normal staff workflow pages load.
4. Try direct access to admin-only routes:
   - `/staff`
   - `/settings`
   - `/integrations`
5. Expected result: staff-only user is redirected to `/unauthorized` or blocked from admin-only access.

## Module Test Notes

Dashboard:

- Confirm summary cards load.
- Confirm numbers are not obviously placeholder-only unless marked as demo.
- Confirm charts/lists do not show console or visible errors.

Calendar and Appointments:

- Create or inspect an appointment if the UI allows it.
- Confirm date/time, patient/client, service, and status fields behave consistently.
- Check whether a calendar item appears after an appointment is created.

Leads:

- Inspect the lead list.
- Confirm lead status/category fields are visible.
- If adding a lead is available, create a test lead and confirm it persists after refresh.

Patients:

- Inspect patient list and detail behavior.
- Confirm no page shows fake-only data without clear demo labeling.

Staff:

- Confirm admin can access.
- Confirm staff-only user cannot access if this is admin-only.

Automation Center:

- Check whether automations are connected, mocked, or placeholder.
- Record any missing webhook/n8n/Make configuration.

Voice Assistant:

- Check whether this is functional, placeholder, or configuration-only.
- Record any required provider such as VAPI or Voiceflow.

Payments:

- Check whether payments are real, mocked, or placeholder.
- Do not run real payment transactions.

Integrations:

- Confirm what integrations are listed.
- Record whether each integration is connected, disconnected, or placeholder.

Settings:

- Confirm admin can access.
- Do not change production-like settings unless Codex/owner approves the specific change.

## Bug Report Format

Use this format for every issue:

```text
Module:
Account used:
Action:
Expected:
Actual:
Screenshot:
Severity: Critical / High / Medium / Low
Notes:
```

