# Dashboard Lovable To Codex 010: Auth Redirect Analysis

Date received: 2026-05-25

Source file from owner:

- `C:\Users\Rosstafari\Downloads\DASHBOARD LOVABLE TO CODEX 6.docx`

## Summary

Dashboard Lovable analyzed the false `/unauthorized` redirect bug.

## Files / Components Involved

- `src/contexts/AuthContext.tsx`
- `src/components/ProtectedRoute.tsx`
- `src/pages/Unauthorized.tsx`
- Indirectly: `src/pages/auth/SignIn.tsx` and admin-only routes such as `/staff`, `/settings`, `/integrations`

## Root Cause Reported By Lovable

Race condition between session restore and role loading:

- `onAuthStateChange` sets the user/session.
- Role loading happens asynchronously after that.
- During the gap, `roles = []`.
- `ProtectedRoute` waits only on the main auth `loading` state, not role loading.
- Protected routes evaluate the signed-in user against an empty role array and redirect to `/unauthorized`.
- Clicking `Home` later works because roles have loaded by then.

This matches the owner symptom exactly.

## Proposed Fix

Frontend-only:

- Add `rolesLoading` or `rolesLoaded` state in `AuthContext.tsx`.
- Reset roles and mark roles as loading whenever a user is present but roles are not fetched yet.
- Expose a combined readiness state such as `ready = !loading && !rolesLoading`.
- In `ProtectedRoute.tsx`, wait for combined readiness before checking `requireRole` or `requireStaff`.
- Keep real unauthorized behavior for accounts with no allowed roles.

## DB Change Needed

Lovable reports no DB change is needed.

## Codex Review

Approved. This is a narrow, appropriate frontend fix for the observed bug.

Guardrails:

- No paid integrations.
- No CRUD build.
- No secrets.
- No DB migration.
- No broad redesign.

