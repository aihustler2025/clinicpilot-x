# Dashboard and Leads QA First Pass

Date: 2026-05-25

Preview:

- `https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app`

## Dashboard Findings

Dashboard is still marked `Demo data`, which is correct.

Visible quick actions:

- New Appointment
- Start AI Call
- Send SMS
- Payment Link

Codex clicked each quick action.

Result:

- No URL change.
- No modal/dialog.
- No visible toast.
- No apparent action.

## Dashboard Recommendation

For MVP, do not show dead quick actions. Replace or disable them until real behavior exists.

Recommended MVP quick actions:

- Add Lead
- New Appointment
- Send Test Notification
- Open Review Queue

Hold/disable:

- Start AI Call
- Send SMS
- Payment Link

Reason:

- AI calls, SMS, and payment links imply VAPI/Twilio/Stripe or other paid provider behavior.
- They should not look active until intentionally wired.

## Leads Findings

Leads is still marked `Demo data`, which is correct.

Current available controls:

- Search by name, email, or phone
- Status filter
- Source filter

Observed:

- Search works on hardcoded demo data.
- Searching `Michael` filtered the lead list to `1 leads` and hid Sarah Johnson.
- There is no visible `Add Lead` / `New Lead` button.
- Because there is no create path and the page is hardcoded, real lead create/update/persistence cannot be tested yet.

## Next Required Build Step

Ask Dashboard Lovable for a scoped Step 2 plan:

1. Dashboard MVP layout/quick-action cleanup.
2. Leads Supabase CRUD:
   - list real leads from `leads`
   - empty state if no leads
   - add lead form
   - edit lead status/notes
   - persist after refresh
   - create test records using plus-addressing
3. Keep SMS/voice/payment disabled until intentionally connected.

