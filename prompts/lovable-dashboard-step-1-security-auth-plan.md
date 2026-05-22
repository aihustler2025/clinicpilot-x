# Dashboard Lovable Step 1: Security And Auth Plan

Send this to Dashboard Lovable next.

```text
Based on your audit, we are choosing Dashboard Lovable as the likely main ClinicPilot X app, but do not implement yet.

First, prepare a Step 1 implementation plan focused only on security, auth, roles, and project memory. This must happen before marketing-page merge, domain connection, n8n, Stripe, Twilio, VAPI, or client demos.

Current critical findings to address:

- External Supabase project is connected: `zglkebeaimtvpynmlrra`.
- Tables exist: appointments, automation_logs, integrations, leads, patients, payments, settings, staff.
- RLS is enabled but all tables currently have public "Allow full access (testing)" policies with USING (true) and WITH CHECK (true).
- There is no auth UI.
- There are no protected routes.
- There are no real app roles.
- No user_roles table or has_role() function exists.
- Some modules use real Supabase tables, but others are mock/hardcoded/local-only.

Please do not change anything yet. Return a detailed implementation plan with:

1. Project memory files you will create/update:
- AGENTS.md
- STATUS.md
- TASKS.md
- DECISIONS.md
- CHANGELOG.md
- PRODUCT_SPEC.md

2. Exact database changes proposed:
- New tables.
- New columns.
- New enums.
- New functions.
- New policies.
- Any foreign keys to add.
- Any existing policies to remove/replace.

3. Exact RLS policy plan for each table:
- appointments
- automation_logs
- integrations
- leads
- patients
- payments
- settings
- staff
- any new profiles/user_roles tables

4. Auth plan:
- Routes to create, such as `/auth`, `/login`, `/signup`, `/forgot-password`.
- Protected route wrapper.
- Redirect behavior.
- Session handling.
- Initial admin bootstrap plan.

5. Role model:
- Roles needed for MVP: admin, staff.
- What each role can read/write.
- Whether public/anonymous users can insert leads through a public contact/demo form.

6. Files/components you expect to touch.

7. Safety checks:
- Confirm no patient/lead/payment data remains publicly readable.
- Confirm public anonymous access is limited to only what is needed for lead capture.
- Confirm no DNS/domain/n8n/payment/voice integrations are changed in this step.

8. Testing plan:
- Anonymous visitor cannot access dashboard data.
- Admin can log in and view leads.
- Staff can log in and view allowed data.
- Public lead form can insert a lead without exposing all leads.

Do not implement yet. Return the plan first for approval.
```
