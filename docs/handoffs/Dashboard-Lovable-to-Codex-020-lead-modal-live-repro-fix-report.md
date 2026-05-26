# Dashboard Lovable to Codex 020: Lead Modal Live Repro Fix Report

Date received: 2026-05-26

Source:

- Owner pasted Dashboard Lovable response directly into Codex chat.

## Summary From Lovable

Dashboard Lovable confirms handoff 018 was not sufficient and reopened the Add/Edit Lead modal persistence bug.

Lovable reports a new patch was applied to the live modal persistence chain.

## Reported Root Cause

The prior fix blocked Radix outside/focus close events, but Add Lead open/draft state still lived only inside the mounted parent tree.

Auth/session re-renders, route guard remounts, or parent remounts could still drop the dialog and wipe form values.

## Files Changed

- `src/pages/Leads.tsx`
- `src/components/leads/LeadFormDialog.tsx`
- `src/components/dashboard/QuickActions.tsx`

## Reported Fix

- Added remount-safe runtime dialog state for Leads Add/Edit.
- Added remount-safe draft persistence for Add/Edit Lead form values.
- Preserved typed values across parent re-render/remount while dialog is open.
- Kept outside click, focus outside, pointer outside, tab switch, and Radix implicit close blocked.
- Kept intentional close paths: save success, Cancel, X, Escape.
- Applied the same defensive open-state handling to Dashboard Quick Actions Add Lead.

## Reported Verification

Lovable reports:

- Traced the open/close chain in `Leads`, `LeadFormDialog`, `QuickActions`, `Dialog`, `AuthContext`, `ProtectedRoute`, and `useLeads`.
- Confirmed no remaining unguarded `setDialogOpen(false)` path except explicit close/save.
- Ran ESLint on changed/relevant files: 0 errors, 1 existing Fast Refresh warning in `AuthContext.tsx`.
- Could not complete live preview verification because the browser session was on the sign-in screen.

## Owner/VA Instructions From Lovable

- Hard refresh or open a fresh tab after this new preview rebuild.
- Sign out/sign in is not required unless already stuck on an old session.
- Step 2B was not started.

## Codex Verification Status

Pending live verification by owner/VA and/or Codex after signed-in preview access is available.

Required verification:

1. Open `/leads`.
2. Click `Add Lead`.
3. Type `Sarah Johnson` in Full Name.
4. Switch tabs for 5+ seconds.
5. Return to ClinicPilot X.
6. Confirm modal is still open and `Sarah Johnson` is still present.
7. Click backdrop/outside the modal while dirty.
8. Confirm modal does not close.
9. Close intentionally with Cancel/X/Escape.
10. Repeat with Edit Lead and typed Notes.

