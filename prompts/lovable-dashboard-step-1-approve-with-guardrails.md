# Dashboard Lovable Step 1 Approval With Guardrails

Send this to Dashboard Lovable if you want to approve Step 1.

```text
Approved to implement Step 1 only: security, auth, roles, and project memory.

Do not implement marketing merge, DNS/domain, n8n, Stripe, Twilio, VAPI, Voiceflow, Google Calendar, payment flows, booking flows, or public lead capture yet.

Please implement Step 1 with these guardrails and clarifications:

1. Project memory files
- Create/update actual project files where possible, not only Lovable memory/knowledge entries:
  - AGENTS.md
  - STATUS.md
  - TASKS.md
  - DECISIONS.md
  - CHANGELOG.md
  - PRODUCT_SPEC.md
- These files should record that Dashboard Lovable is now the main app candidate, Marketing Lovable is on hold, and Step 1 is security/auth only.

2. Database/RLS
- Preserve all existing tables and rows.
- Do not drop existing data.
- Drop/replace the public "Allow full access (testing)" policies.
- Ensure anon/public cannot select, update, delete, or broadly insert into patient, lead, appointment, payment, staff, settings, integrations, or automation log tables.
- Use role-scoped policies for authenticated users only.
- Create profiles, user_roles, app_role enum, has_role(), and is_staff() as planned.
- Use SECURITY DEFINER functions with a fixed search_path.

3. Admin bootstrap
- Do not rely on an unsafe or vague first-user auto-admin flow.
- If the first user receives a temporary staff role, provide the exact SQL instruction needed to promote the owner account to admin.
- After implementation, clearly state the owner/admin setup steps.
- Do not expose any admin promotion capability in the public frontend.

4. Public lead capture
- Do not enable anonymous public lead insertion in Step 1.
- We will handle public contact/demo form lead capture in Step 2 through a restricted path, likely either a tightly scoped insert policy or an edge function/webhook.
- Record this in TASKS.md as pending.

5. Auth routes and protection
- Add /auth, /auth/forgot-password, /auth/reset-password, and /unauthorized.
- Protect all existing dashboard routes.
- Admin-only routes initially: /staff, /settings, /integrations.
- All other app routes require any staff role.
- Add sign-out and role display in the app shell/header.

6. Testing and reporting
- Run the Supabase linter/security scan if available.
- Confirm no public USING (true) / WITH CHECK (true) policies remain.
- Confirm signed-out users cannot access dashboard data.
- Confirm authenticated users without roles cannot access dashboard pages.
- Confirm admin can access all dashboard sections.
- Confirm non-admin staff cannot access admin-only sections.

After implementation, report back with:

1. Files changed.
2. Tables/functions/enums created.
3. Policy names created/dropped.
4. Auth routes added.
5. Manual owner/admin setup steps.
6. Test results.
7. Any errors, warnings, or remaining security risks.

Proceed with Step 1 only.
```
