# Codex To Dashboard Lovable 010: Auth Redirect Bug and Functional QA Plan

Date: 2026-05-25

To: Dashboard Lovable  
From: Codex  
Project: ClinicPilot X Dashboard

## Context

Codex verified handoff 008 in the live preview and accepts it as complete for the approved scope.

Verification notes:

- `03-lovable/dashboard-handoff-008-verification-2026-05-25.md`

Now we need to fix one auth/navigation bug before deeper functional testing.

## Bug: Admin Sometimes Lands On `/unauthorized`

The owner reports this flow:

1. Owner signs in using `donjericho617@gmail.com`.
2. App sometimes lands on `/unauthorized`.
3. `/unauthorized` says the account is signed in but has not been granted access.
4. Owner clicks `Home`.
5. App takes the owner into the dashboard successfully.

Codex also verified that the active session can access admin/sidebar routes such as `/payments`, `/settings`, `/integrations`, etc. The header shows the `admin` role.

This means the owner account does have access. The issue is likely one of:

- protected route checks run before roles finish loading
- role state defaults to unauthorized while Supabase/profile/user_roles reads are still pending
- unauthorized page does not re-check/refresh role state before displaying the denial
- redirect target after login is stale or points to an admin-only route before role context is ready
- role array/string comparison mismatch during initial auth hydration

## Required Fix

Fix the auth/protected-route flow so `donjericho617@gmail.com` never sees `/unauthorized` once the app has confirmed the user has `admin` or allowed staff role access.

Expected behavior:

1. While auth/roles are loading, show a loading state, not `/unauthorized`.
2. If the user has `admin`, allow access to all current admin routes.
3. If the user has only `staff`, allow staff-safe routes and block admin-only routes.
4. If role lookup fails, show an error/retry state or sign-in-safe state, not a false permanent denial.
5. `/unauthorized` should include a reliable re-check or should not render until role loading has completed.
6. After login, route the admin to `/` unless there is a valid intended route and roles are confirmed.

## Routes To Test After Fix

Use `donjericho617@gmail.com` as admin:

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

Expected: no `/unauthorized` for the admin account.

## Scope Guardrails

Keep this task focused:

- No paid integrations.
- No provider activation.
- No secrets.
- No broad redesign.
- No destructive SQL.
- No database migration unless absolutely required and reviewed by Codex first.
- No CRUD build yet unless you explicitly propose it as a separate next step.

## Functional QA Plan After Auth Bug

After this auth bug is fixed and verified, we will begin functional testing module-by-module.

Planned order:

1. Leads: create/read/update/persistence.
2. Patients: create/read/update/persistence.
3. Appointments: create/read/update/persistence.
4. Calendar: appointment visibility and date behavior.
5. Staff role: create staff-only account and verify admin route blocking.
6. Automation Center: define email intake workflow and integration requirements.
7. Payments: keep as demo/read-only until Stripe/payment mode is intentionally planned.
8. Voice Assistant: keep as demo/read-only until VAPI/voice provider is intentionally planned.

## Required Response

Please reply with:

1. Files/components involved in the auth redirect bug.
2. The exact root cause you find.
3. Your proposed fix.
4. Whether any DB change is needed.
5. Your test checklist.

Do not switch into a broad CRUD build yet. Fix the auth redirect bug first.

