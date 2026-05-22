# Lovable QA Protocol

Updated: 2026-05-22

## Operating Model

Codex is the project manager and technical QA lead for ClinicPilot X.

Lovable can propose plans and implement code, but Lovable's claims are not treated as verified until Codex checks them.

## Rule

Do not mark a Lovable task complete from Lovable's chat response alone.

Completion requires verification through one or more of:

- Lovable preview inspection.
- Source code review or export/GitHub sync review.
- Supabase table/policy/function inspection.
- Dashboard/app behavior testing.
- Browser testing of login, routes, redirects, forms, and role behavior.
- DNS/domain verification when domain work begins.
- n8n/webhook testing when automation work begins.

## Verification Workflow

1. Codex writes the prompt/task for Lovable.
2. Owner sends prompt to Lovable.
3. Lovable replies or implements.
4. Owner sends Lovable response/artifacts back to Codex.
5. Codex reviews the response and identifies what must be verified.
6. If access is needed, Codex asks owner for the specific login/session/page required.
7. Codex verifies directly where possible.
8. Codex reports:
   - verified complete
   - incomplete
   - inconsistent
   - needs correction
   - blocked pending access
9. Codex updates `STATUS.md`, `TASKS.md`, `DECISIONS.md`, and `CHANGELOG.md`.

## Access Expectations

If verification requires access to Lovable, Supabase, GitHub, GoDaddy, SiteGround, n8n, Resend, Gmail, or another service, Codex should say exactly which account/page is needed and why.

Do not paste passwords into chat. Use browser login/session access or safe account recovery flows.

## Current Immediate Verification Need

Dashboard Lovable reports Step 1 is complete, but Codex has not independently verified:

- Auth user list.
- Owner/admin role.
- RLS policies in Supabase.
- Protected route behavior.
- Admin-only route behavior.
- Build/runtime behavior after sign-in.

Next prompt to Lovable should request the safe access/recovery details needed for verification.
