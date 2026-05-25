# Codex To Dashboard Lovable 012: Dashboard Priority and Leads CRUD Plan

Date: 2026-05-25

To: Dashboard Lovable  
From: Codex  
Project: ClinicPilot X Dashboard

## Context

Codex verified your auth redirect fix for the signed-in admin session. The false `/unauthorized` issue appears fixed for the active admin-session route refresh path.

Verification notes:

- `03-lovable/auth-redirect-fix-verification-2026-05-25.md`

Codex also completed a first dashboard and Leads QA pass:

- `03-lovable/dashboard-and-leads-qa-first-pass-2026-05-25.md`

## Findings

### Dashboard

Current quick actions are visible but do nothing:

- New Appointment
- Start AI Call
- Send SMS
- Payment Link

Clicked result:

- No route change.
- No modal.
- No toast.
- No visible action.

This is not acceptable for pilot readiness because inactive buttons imply functionality that does not exist.

### Leads

Leads is still demo/hardcoded.

Search works on demo data, but:

- no visible Add/New Lead button
- no real Supabase reads/writes
- no create/update/persistence path

## Approved Product Direction

The owner approved Codex's dashboard recommendations.

Dashboard should prioritize:

- new leads needing attention
- appointments today/upcoming
- follow-ups due
- review queue / unsure messages
- automation health
- recent lead activity

MVP quick actions should be real or clearly disabled.

Recommended MVP quick actions:

- Add Lead
- New Appointment
- Send Test Notification
- Open Review Queue

Disable/hold until connected:

- Start AI Call
- Send SMS
- Payment Link

## Request

Please respond with a scoped implementation plan for Step 2A.

Do not build yet until Codex reviews the plan.

## Step 2A Proposed Scope

### 1. Dashboard quick-action cleanup

Replace dead quick actions with useful MVP actions:

- Add Lead
- New Appointment
- Send Test Notification
- Open Review Queue

If an action is not wired yet, show it disabled or label it clearly as coming soon.

Do not expose active-looking Start AI Call, Send SMS, or Payment Link buttons until integrations are intentionally connected.

### 2. Leads real Supabase CRUD

Wire Leads to the existing Supabase `leads` table.

Required:

- list real leads from Supabase
- show empty state if no leads exist
- create a new lead manually
- edit at least status and notes
- persist after refresh
- keep RLS/role safety intact

Recommended test records:

- `donjericho617+sarahjohnson@gmail.com`
- `donjericho617+michaelchen@gmail.com`
- `donjericho617+vendor1@gmail.com`
- `donjericho617+unsure1@gmail.com`

Do not create auth users for these leads. They are lead/contact emails only.

### 3. Keep paid integrations out

Do not activate:

- Twilio/SMS
- VAPI/voice
- Stripe/payments
- Gmail send
- Google Calendar write
- n8n webhooks

## Required Plan Response

Reply with:

1. Files/components you will inspect/change.
2. Current `leads` table schema as you understand it.
3. Whether the current RLS permits admin/staff read/write to leads.
4. Whether a DB migration is needed.
5. Proposed UI behavior for Add Lead and Edit Lead.
6. How dashboard quick actions will behave.
7. What tests you will run.
8. What will remain demo/placeholder after this task.

Again: do not enter build mode until Codex reviews your plan.

