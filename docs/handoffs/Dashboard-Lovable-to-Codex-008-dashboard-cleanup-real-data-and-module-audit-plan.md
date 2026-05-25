# Dashboard Lovable To Codex 008: Dashboard Cleanup, Real Data, and Module Audit Plan

Date received: 2026-05-25

Source file from owner:

- `C:\Users\Rosstafari\Downloads\DASHBOARD LOVABLE TO CODEX 4.docx`

## Summary

Dashboard Lovable responded to Codex handoff 008 with a scoped plan. The plan stays within the requested guardrails:

- No paid integrations activated.
- No redesign.
- No database migration.
- No destructive SQL.
- No secrets added.
- No external providers wired.
- It will make the app honest by showing real signed-in/profile/settings data where possible and tagging hardcoded list modules as demo data.

## Files Lovable Plans To Inspect

- `src/pages/Dashboard.tsx`
- `src/pages/CalendarView.tsx`
- `src/pages/Appointments.tsx`
- `src/pages/Leads.tsx`
- `src/pages/Patients.tsx`
- `src/pages/Staff.tsx`
- `src/pages/Automation.tsx`
- `src/pages/VoiceAssistant.tsx`
- `src/pages/Payments.tsx`
- `src/components/dashboard/*`
- `src/components/Header.tsx`

## Files Lovable Plans To Change

- `src/pages/Settings.tsx`
- `src/pages/Profile.tsx`
- `src/pages/Integrations.tsx`
- A small shared `DemoDataBadge` component
- `STATUS.md`
- `TASKS.md`

## Lovable's Current Data Audit

Lovable reports:

- Auth/Header role badge: Supabase-backed through `AuthContext`, `user_roles`, and `profiles`
- Dashboard stats/alerts/today: hardcoded
- Calendar: hardcoded
- Appointments: hardcoded
- Leads: hardcoded
- Patients: hardcoded
- Staff: hardcoded
- Automation Center: hardcoded
- Voice Assistant: hardcoded
- Payments: hardcoded
- Integrations: hardcoded statuses plus stale Supabase placeholder
- Settings: hardcoded demo values
- Profile: local state

Lovable reports current DB row counts:

- `profiles`: 1
- all other operational tables: 0

## What Lovable Says Will Remain Placeholder

- Dashboard, Calendar, Appointments, Leads, Patients, Staff, Automation, Voice Assistant, and Payments data will remain hardcoded for this task, but visibly tagged as `Demo data`.
- Settings/Profile edit/save flow remains follow-up work.
- Integrations provider tiles will be shown as `Not connected`.
- No test users, leads, patients, or appointments will be auto-created in code or chat.

## Codex Review

This plan is acceptable for build approval as long as Lovable's build mode matches this exact scope.

Required post-build Codex verification:

1. Settings/Profile display the real signed-in email `donjericho617@gmail.com`.
2. Fake `Dr. Sarah Johnson` / `sarah.johnson@clinic.com` owner data is gone from owner profile/settings.
3. Integrations no longer says Supabase is missing or requires `Connect Supabase`.
4. Provider tiles are not marked connected without verified credentials.
5. Demo data badges appear on hardcoded modules.
6. No paid external integrations are activated.
7. No unexpected database migration was applied.

