# Dashboard Lovable to Codex 018: Lead Modal Tab-Switch Completion Report

Date received: 2026-05-26

Source file from owner:

- `C:\Users\Rosstafari\Downloads\DASHBOARD LOVABLE TO CODEX 12.docx`

## Summary From Lovable

Dashboard Lovable reports the Add/Edit Lead modal no longer clears typed values or closes when the tester switches browser tabs/windows.

## Reported Root Cause

Two issues were involved:

- Supabase fires `TOKEN_REFRESHED` on `onAuthStateChange` when the tab regains focus.
- `AuthContext` calls `setUser(newSession.user)` with a fresh user object.
- `LeadFormDialog` had `user` in a seeding effect dependency array, causing `form.reset(emptyDefaults)` to run again when auth refreshed.
- Radix Dialog outside-focus/pointer behavior could also fire on some tab/focus changes.

## Reported Fix

Changed `src/components/leads/LeadFormDialog.tsx`:

- Seeding effect now depends only on `[open, lead?.id]`.
- Added `lastKeyRef` so the form resets once per open/lead transition.
- Added `onInteractOutside`, `onPointerDownOutside`, and `onFocusOutside` guards on `DialogContent`.
- Dirty forms should not be dismissed by tab/window switching or outside focus/pointer events.

## Reported Verification

Lovable reports:

- Build is clean.
- Dialog seeds defaults once on open.
- Auth refresh no longer resets the form.
- Submit, Cancel, X, and Escape close paths are unchanged.
- Edit mode still reseeds when switching to a different `lead.id`.

## Remaining Risk

Lovable notes `onFocusOutside` is fully suppressed, so clicking behind the modal will not dismiss an empty Add Lead form. Users must use Cancel/X/Escape.

This matches current QA intent because accidental modal dismissal is more damaging than requiring explicit close behavior.

## Codex Verification Status

Pending live preview verification.

Owner reports the VA may still be seeing the old behavior, likely because the VA is testing a stale/unpublished build or a different URL.

