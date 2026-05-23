# Codex To Dashboard Lovable 007: Public Repo Context And Admin Access

Suggested response filename: `Dashboard-Lovable-to-Codex-007-public-repo-context-and-admin-access-response.md`

## Context

We are building **ClinicPilot X**, a Buzzooka-owned product for clinics, med spas, dental practices, salons, and similar service businesses.

The current decision is:

- **Dashboard Lovable** is the main app going forward.
- **Marketing Lovable** is on hold for now.
- Marketing pages will likely be ported into Dashboard Lovable later.
- We are not doing domain/DNS, n8n, Stripe, Twilio, VAPI, Voiceflow, Google Calendar, or marketing merge yet.

The current phase is:

**Verify Step 1: security, auth, roles, and project memory.**

You reported that Step 1 is complete, including:

- auth routes
- protected dashboard routes
- admin-only route handling
- role-scoped RLS
- project memory files

Codex must verify this before we move to Step 2.

## Shared GitHub Repo

The shared source of truth is now public:

`https://github.com/aihustler2025/clinicpilot-x`

Please use GitHub as the shared source of truth, not the owner's local D drive.

## Files To Read

Please read these files from GitHub:

- `AGENTS.md`
- `STATUS.md`
- `TASKS.md`
- `DECISIONS.md`
- `CHANGELOG.md`
- `PRODUCT_SPEC.md`
- `docs/NAMING.md`

Direct links:

- https://github.com/aihustler2025/clinicpilot-x/blob/main/AGENTS.md
- https://github.com/aihustler2025/clinicpilot-x/blob/main/STATUS.md
- https://github.com/aihustler2025/clinicpilot-x/blob/main/TASKS.md
- https://github.com/aihustler2025/clinicpilot-x/blob/main/DECISIONS.md
- https://github.com/aihustler2025/clinicpilot-x/blob/main/CHANGELOG.md
- https://github.com/aihustler2025/clinicpilot-x/blob/main/PRODUCT_SPEC.md
- https://github.com/aihustler2025/clinicpilot-x/blob/main/docs/NAMING.md

## Handoff Files

Handoffs live here:

`docs/handoffs/`

Important recent handoffs:

- https://github.com/aihustler2025/clinicpilot-x/blob/main/docs/handoffs/Codex-to-Dashboard-Lovable-004-admin-access-recovery.md
- https://github.com/aihustler2025/clinicpilot-x/blob/main/docs/handoffs/Codex-to-Dashboard-Lovable-005-handoff-naming-protocol.md
- https://github.com/aihustler2025/clinicpilot-x/blob/main/docs/handoffs/Codex-to-Dashboard-Lovable-006-shared-repo-sync-confirmation.md
- https://github.com/aihustler2025/clinicpilot-x/blob/main/docs/handoffs/Codex-to-Dashboard-Lovable-007-public-repo-context-and-admin-access.md

## What We Need From You Now

Do not implement Step 2 yet.

Please help us verify Step 1 and establish owner/admin access safely.

Do **not** reveal, generate, or expose passwords.

Please answer:

1. What is the current preview URL for Dashboard Lovable?
2. What is the exact Supabase project ref connected to Dashboard Lovable?
3. Is email confirmation currently required for sign-up?
4. Are there existing Supabase Auth users?
   - If yes, list only email addresses and user IDs if accessible.
   - Do not reveal passwords.
5. Is there already an admin user in `public.user_roles`?
   - If yes, list the email and role mapping.
   - Do not reveal passwords.
6. What is the safest way for the owner to get admin access now?

## Please Provide Exact SQL

Please provide:

1. SQL to inspect existing auth users and their roles.
2. SQL to promote a chosen owner email to `admin`.
3. SQL to verify no public/anon full-access policies remain.
4. SQL to verify `has_role()` and `is_staff()` exist and are callable only as intended.

## Please Provide Manual Test Checklist

After admin access is created, we need to verify:

1. Signed-out visitor hitting dashboard route redirects to `/auth`.
2. Owner/admin can sign in.
3. Admin can access `/staff`, `/settings`, `/integrations`.
4. Non-admin staff cannot access admin-only routes.
5. Sign-out works.
6. Role badge/user email displays correctly.
7. Existing data pages do not leak to anonymous users.

## Do Not Do Yet

- Do not start Step 2.
- Do not connect n8n.
- Do not connect domain/DNS.
- Do not merge marketing pages.
- Do not add Stripe, Twilio, VAPI, Voiceflow, Google Calendar, or payment flows.
- Do not enable public lead capture yet.

Please respond using the suggested filename:

`Dashboard-Lovable-to-Codex-007-public-repo-context-and-admin-access-response.md`
