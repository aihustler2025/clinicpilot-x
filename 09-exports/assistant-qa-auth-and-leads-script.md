# Assistant QA Script: Auth Bug and Leads First Pass

Updated: 2026-05-25

## Purpose

Use this script after Lovable fixes the `/unauthorized` redirect bug. The goal is to confirm that the admin account can reliably enter the app, then begin the first real functional test area: Leads.

## Test Account

Admin:

- `donjericho617@gmail.com`

Do not record or share the password.

## Part 1: Auth Redirect Test

1. Open:
   - `https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app/auth`
2. Sign in as `donjericho617@gmail.com`.
3. Confirm the app lands on Dashboard `/` or another valid dashboard route.
4. Confirm you do not see `/unauthorized`.
5. Refresh the browser.
6. Confirm you still do not see `/unauthorized`.
7. Directly visit each route:
   - `/`
   - `/calendar`
   - `/appointments`
   - `/leads`
   - `/patients`
   - `/staff`
   - `/automation`
   - `/voice-assistant`
   - `/payments`
   - `/integrations`
   - `/settings`
   - `/profile`
8. Expected result: admin account can access all routes without a false access-denied page.

## Part 2: Leads Module Observation

Do not create or delete anything yet unless Codex says the module has real save behavior.

1. Open `/leads`.
2. Confirm whether the page shows a `Demo data` badge.
3. Look for buttons or actions:
   - Add Lead
   - New Lead
   - Edit
   - Convert
   - Assign
   - Delete
4. Search for a test name such as `Sarah`.
5. Use filters:
   - status filter
   - source filter
6. Record whether filters visibly change the table.

## Bug Report Format

```text
Module:
Step:
Expected:
Actual:
Screenshot:
Severity:
Notes:
```

## Do Not Test Yet

Do not test real email sending, SMS, calls, Stripe payments, VAPI calls, Gmail sending, or Google Calendar writes until Codex confirms those integrations are intentionally connected.

