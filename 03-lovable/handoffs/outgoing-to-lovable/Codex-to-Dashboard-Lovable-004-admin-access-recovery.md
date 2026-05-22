# Dashboard Lovable Admin Access Recovery Prompt

Send this to Dashboard Lovable next.

```text
Step 1 looks complete. Before we move to Step 2, we need to safely establish owner/admin access and verify the protected app.

Please do not reveal, generate, or expose any passwords. We only need a safe admin access/recovery procedure.

Please answer:

1. What is the current preview URL for the Dashboard Lovable app?
2. What is the exact Supabase project ref connected to this app?
3. Is email confirmation currently required for sign-up?
4. Are there any existing Supabase Auth users?
   - If yes, list only the email addresses and user IDs if accessible.
   - Do not reveal passwords.
5. Is there already an admin user in public.user_roles?
   - If yes, list the email and role mapping.
   - Do not reveal passwords.
6. What is the safest way for the owner to get admin access right now?

Please provide exact steps for one of these paths:

Path A: Create new owner account
- Owner signs up at `/auth`.
- Then provide the exact SQL to promote that email to admin.

Path B: Existing owner account found
- Provide the exact Supabase Auth reset-password path or instructions.
- Provide the SQL to ensure that account has admin role.

Please also provide:

7. The exact SQL query to inspect auth users and current roles.
8. The exact SQL to promote a chosen owner email to admin.
9. The exact SQL to verify no anon/public full-access policies remain.
10. The manual test checklist after admin access is created:
    - signed-out dashboard access redirects to `/auth`
    - owner/admin can sign in
    - admin can access `/staff`, `/settings`, `/integrations`
    - non-admin staff cannot access admin-only routes
    - sign-out works

Do not implement Step 2 yet.
Do not connect n8n yet.
Do not connect domain/DNS yet.
Do not merge marketing pages yet.
```
