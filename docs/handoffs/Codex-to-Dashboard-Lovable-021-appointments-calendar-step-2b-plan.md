# Codex to Dashboard Lovable 021: Appointments and Calendar Step 2B Plan

Mode: Plan

Action requested: Inspect the current Appointments and Calendar implementation and propose a Step 2B build plan. Do not build yet.

## Context

Step 2A focused on Leads. The owner reports the Add/Edit Lead modal issue appears fixed, while assistant QA is continuing.

Next major module:

- Appointments
- Calendar

The owner looked at Calendar and believes it is still using demo data. The owner wants a polished internal calendar/appointments system that can later connect to Google Calendar, Calendly, chatbot booking, website/contact form inquiries, and email intake.

Read this strategy first:

`02-product/appointments-calendar-step-2b-strategy.md`

Also read:

- `STATUS.md`
- `TASKS.md`
- `02-product/dashboard-priority-review.md`
- `02-product/lead-source-strategy.md`
- `00-admin/cost-and-api-watchlist.md`

## Product Direction

ClinicPilot X should be the smart front-desk layer, not a forced replacement for every clinic's practice-management scheduler on day one.

For MVP:

- Appointment requests should not be auto-confirmed by default.
- Staff should review and approve/reschedule.
- High-value/high-intent requests should be prioritized.
- The internal calendar should work even without Google Calendar or Calendly.

## Required Step 2B Plan

Please inspect the current code and Supabase schema, then propose a concrete build plan covering:

1. Current state of `/appointments` and `/calendar`.
2. Which data is mock/demo versus real Supabase-backed.
3. Existing `appointments` table fields and whether migration is needed.
4. Whether `patients`, `leads`, and `staff` can be linked safely.
5. Recommended appointment/request statuses.
6. Recommended calendar UI component approach already present in the app.
7. Whether drag/drop rescheduling is currently practical.
8. How to add appointment detail modal/drawer.
9. How to add PriorityBook fields/labels without AI dependency.
10. What should stay explicitly out of scope.

## Desired MVP Behavior

Appointments:

- Staff can create appointment/request manually.
- Staff can link to an existing lead/patient if possible.
- Staff can edit date/time/service/status/provider/notes.
- Appointment/request persists after refresh.
- Search/filter by status, provider, service, priority.

Calendar:

- Reads real appointments from Supabase.
- Shows month/week/day or the best practical subset for MVP.
- Click appointment to open details.
- Create appointment from a selected date/time if practical.
- Drag/reschedule only if it can be done safely and professionally.
- Color-code by status and/or priority.

PriorityBook:

- Rule-based scoring only for now.
- Fields can include `priority_score`, `priority_label`, and `priority_reason`.
- No AI scoring dependency yet.

External integrations:

- Show Google Calendar, Calendly, Google Meet, Zoom, etc. as `Not connected` unless real credentials/config exist.
- It is okay to include fields for future external IDs/links.
- It is okay to allow staff to paste a virtual meeting link manually.

## Guardrails

Do not:

- Start Step 2B build until Codex approves the plan.
- Enable Google Calendar, Calendly, Stripe, Twilio, VAPI, n8n, or paid APIs.
- Claim integrations are connected without proof.
- Seed fake production data.
- Change auth/RLS broadly.
- Break existing Leads module.

## Response Back To Codex

Please respond with:

1. Summary
2. Current `/appointments` state
3. Current `/calendar` state
4. Current Supabase `appointments` schema
5. Proposed migrations, if any
6. Proposed files to change
7. Proposed UX behavior
8. Out-of-scope items
9. Testing/verification plan
10. Any questions that block implementation

