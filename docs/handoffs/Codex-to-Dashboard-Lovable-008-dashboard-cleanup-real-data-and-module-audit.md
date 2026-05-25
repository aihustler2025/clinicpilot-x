# Codex To Dashboard Lovable 008: Dashboard Cleanup, Real Data, and Module Audit

Date: 2026-05-25

To: Dashboard Lovable  
From: Codex  
Project: ClinicPilot X Dashboard  
Repo source of truth: `https://github.com/aihustler2025/clinicpilot-x`

## Context

Codex verified the live Dashboard Lovable preview directly in the in-app browser using the owner admin account:

- Preview URL: `https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app/`
- Logged-in email: `donjericho617@gmail.com`
- Role badge shown in header: `admin`

Admin route access is working at the route level. The following modules loaded without redirecting to `/auth` or `/unauthorized`:

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

Codex saved the detailed live inventory here:

- `03-lovable/dashboard-live-admin-inventory-2026-05-25.md`

Please read that file before implementing.

## Goal

Clean up the dashboard so it is honest, testable, and ready for a fast MVP pilot.

This is not a broad redesign task. Do not rebuild the app. Make focused changes that remove misleading placeholder messaging, connect visible account/profile state to real Supabase data where possible, and clearly distinguish real data from demo data.

## Required Changes

### 1. Settings must not show fake owner data

Current issue:

Settings shows demo values:

- `Dr. Sarah Johnson`
- `sarah.johnson@clinic.com`
- `Advanced Cosmetic Surgery Center`

But the logged-in admin is:

- `donjericho617@gmail.com`

Fix:

- Settings should display the real signed-in user email from Supabase Auth.
- If profile/clinic fields do not exist yet, show empty editable fields or a clear setup state.
- Do not show fake names/emails as if they are real.
- If needed, use `profiles` and/or `settings` tables already created during Step 1.

### 2. Integrations must not claim Supabase is missing

Current issue:

Integrations page says:

- `Backend Integration Required`
- `Connect Supabase`

But Supabase is already connected and powering auth/roles.

Fix:

- Remove or replace this stale placeholder.
- If an integration is not actually connected, mark it as `Not connected` or `Coming soon`.
- Do not label Google Calendar, Stripe, Gmail, etc. as `connected` unless there is real credential/config evidence in Supabase or environment variables.

### 3. Clarify real data versus demo data

Current issue:

Many modules show sample/demo records and 2024 dates. This can confuse the owner and client testers.

Fix:

- Audit Dashboard, Calendar, Appointments, Leads, Patients, Staff, Automation Center, Voice Assistant, Payments, Integrations, and Settings.
- For each module, identify whether displayed data is:
  - Supabase-backed real data
  - seeded demo data
  - hardcoded mock data
  - placeholder UI only
- Prefer replacing hardcoded fake records with real Supabase records where tables already exist.
- If a module is still placeholder-only, add subtle internal/test-mode labeling such as `Demo data` or `Not connected yet`.
- Avoid public-facing or client-facing copy that pretends integrations are live before they are.

### 4. Prepare safe real test data

The owner wants quick MVP testing with realistic data.

Use plus-addressing for test people where appropriate:

- `donjericho617+sarahjohnson@gmail.com`
- `donjericho617+michaelchen@gmail.com`
- `donjericho617+emmadavis@gmail.com`
- `donjericho617+staff1@gmail.com`

Do not create real passwords in code or chat. If auth users are needed, explain the safest owner action and/or provide SQL-free UI steps.

Recommended first test records:

- 2 leads
- 2 patients
- 2 appointments
- 1 staff-only user/account

### 5. Do not implement paid/provider integrations yet

Do not wire Stripe, Twilio, VAPI, Voiceflow, Gmail send, Google Calendar write, or n8n webhooks in this task unless they already exist and can be verified safely.

Instead:

- Make the UI honest about connection status.
- Leave clear TODO notes or project memory updates describing what is required to connect each provider.

## Required Response

Before build mode, reply with a short plan that includes:

1. Which files/components you will inspect/change.
2. Which modules are currently Supabase-backed versus mock/hardcoded, based on code inspection.
3. Whether `profiles`, `settings`, `leads`, `patients`, `appointments`, `staff`, `payments`, `integrations`, and `automation_logs` are currently read/written by the UI.
4. Any database migration needed, if any.
5. A clear list of what will remain placeholder after this task.
6. Confirmation that no paid external integrations will be activated.

Do not claim completion until Codex verifies the live preview after your changes.

