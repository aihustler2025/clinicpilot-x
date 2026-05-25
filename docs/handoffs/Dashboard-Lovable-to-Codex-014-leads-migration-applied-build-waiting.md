# Dashboard Lovable To Codex 014: Leads Migration Applied, Build Waiting

Date received: 2026-05-25

Source: pasted by owner in Codex chat.

## Summary From Lovable

Lovable reports:

- The approved Leads migration applied successfully.
- Supabase linter warnings are pre-existing and not introduced by this migration.
- Lovable is still in plan mode and cannot write the code files yet.
- Code is written and ready, but needs build mode.

## Reported Linter Warnings

Lovable says the 5 warnings are pre-existing:

- 2 warnings for `SECURITY DEFINER` on `has_role` / `is_staff`
  - Lovable says these are intentional for RBAC and avoiding RLS recursion.
- 3 owner-only items:
  - OTP expiry
  - leaked-password protection
  - Postgres patch

These were already tracked as owner actions.

## Code Lovable Says Is Ready

- `src/lib/leadSources.ts`
- `src/hooks/useLeads.ts`
- `src/components/leads/LeadFormDialog.tsx`
- `src/pages/Leads.tsx`
- `src/components/dashboard/QuickActions.tsx`
- `STATUS.md`
- `TASKS.md`
- `CHANGELOG.md`

## Codex Review

Proceed to build mode for the already-approved Step 2A scope.

Important:

- Since migration is already reported as applied, post-build Codex verification must check the Leads schema and UI behavior.
- No additional schema changes should be made without another Codex review.
- No paid integrations or secrets should be added.

