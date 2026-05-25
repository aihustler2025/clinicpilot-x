# Dashboard Lovable To Codex 012: Dashboard Quick Actions and Source-Aware Leads CRUD Plan

Date received: 2026-05-25

Source file from owner:

- `C:\Users\Rosstafari\Downloads\DASHBOARD LOVABLE TO CODEX 8.docx`

## Summary

Dashboard Lovable responded with a Step 2A plan for Dashboard quick actions and source-aware Leads CRUD.

## Proposed Frontend Changes

Inspect:

- `src/pages/Leads.tsx`
- `src/pages/Dashboard.tsx`
- `src/components/dashboard/QuickActions.tsx`
- `src/integrations/supabase/types.ts`

Create:

- `src/pages/leads/LeadFormDialog.tsx`
- `src/hooks/useLeads.ts`
- `src/lib/leadSources.ts`

Change:

- `src/pages/Leads.tsx`
- `src/components/dashboard/QuickActions.tsx`
- `STATUS.md`
- `TASKS.md`
- `CHANGELOG.md`

## Current Leads Table Reported By Lovable

Current columns:

- `id`
- `created_at`
- `status`
- `source`
- `service`
- `notes`
- `patient_id`

Current enums:

- `lead_status`: `New`, `Contacted`, `Awaiting Confirmation`, `Converted`, `Followed-Up`
- `lead_source`: `Chatbot`, `Manual`, `Messenger`, `WhatsApp`

Reported problem:

- contact name/email/phone are not on `leads`; they are only reachable through `patient_id -> patients`
- this is not enough for source-aware lead capture before a lead becomes a patient

## Proposed Additive DB Migration

Lovable proposes one small additive migration:

- extend `lead_source` enum with `Website`, `Email`, `Instagram`, `Ads`, `Other`
- add nullable fields:
  - `source_detail text`
  - `message text`
  - `assigned_to uuid references auth.users(id) on delete set null`
  - `follow_up_at timestamptz`
  - `last_contacted_at timestamptz`
  - `consent boolean default false`
  - `contact_name text`
  - `contact_email text`
  - `contact_phone text`
  - `updated_at timestamptz default now()`
- add/update trigger using `update_updated_at_column()`
- add indexes on:
  - `status`
  - `source`
  - `created_at desc`
  - `follow_up_at`

No drops, no data deletion, no RLS changes.

## Proposed Leads UI

Add Lead modal:

- contact name required
- email
- phone
- source dropdown
- source detail
- service interest
- status
- assigned staff
- follow-up date
- notes/message

Edit Lead:

- status and notes at minimum
- also assigned staff, follow-up, source detail

List:

- Supabase query ordered by `created_at desc`
- page size 50
- columns for contact, source, service, status, assigned, follow-up, last contacted, actions
- client-side search/filter over loaded page
- empty state

## Proposed Dashboard Quick Actions

Replace dead actions with:

- Add Lead
- New Appointment
- Send Test Notification
- Open Review Queue

Remove:

- Start AI Call
- Send SMS
- Payment Link

## Codex Review

This plan is directionally correct and matches the owner vision.

Codex recommends a custom approval message instead of blindly clicking Approve because the plan includes a real database migration.

Approval should explicitly allow:

- the listed additive migration only
- no destructive changes
- no paid integrations
- no external webhooks yet
- no auth user creation for leads

Required post-build verification:

1. Add the recommended test leads.
2. Refresh and confirm persistence.
3. Edit status/notes/follow-up and confirm persistence.
4. Confirm dashboard quick actions no longer include dead SMS/voice/payment actions.
5. Confirm no paid integrations/secrets were added.

