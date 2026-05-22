# Dashboard Lovable To Codex 1

Source: `C:/Users/Rosstafari/Downloads/DASHBOARD LOVABLE TO CODEX 1.docx`

```text
DASHBOARD LOVABLE TO CODEX 1

Step 1 — Security, Auth, Roles, Project Memory

The database migration has already been approved and applied. What remains is the application code and project memory files. Switching to build mode will let me complete the rest.

Already done (database)

Added enum app_role (admin, doctor, staff, receptionist).

Created public.profiles and public.user_roles with RLS enabled.

Created has_role(), is_staff(), handle_new_user(), update_updated_at_column() functions.

on_auth_user_created trigger auto-creates a profile + temporary staff role for every new signup.

Dropped all 8 "Allow full access (testing)" policies on appointments, automation_logs, integrations, leads, patients, payments, settings, staff.

Replaced with strict, role-scoped policies (staff read/write on operational tables; admin-only writes on payments, staff, settings, integrations; admin-only deletes on PII tables; no anon access anywhere).

Revoked PUBLIC/anon EXECUTE on internal helper functions.

Still to build (needs build mode)

New files

src/contexts/AuthContext.tsx — session + roles provider (subscribes to onAuthStateChange BEFORE getSession).

src/components/ProtectedRoute.tsx — gates routes by auth + optional role.

src/pages/auth/SignIn.tsx — sign-in + sign-up tabs.

src/pages/auth/ForgotPassword.tsx

src/pages/auth/ResetPassword.tsx

src/pages/Unauthorized.tsx

Edited files

src/App.tsx — wrap in AuthProvider, add /auth, /auth/forgot-password, /auth/reset-password, /unauthorized; wrap all app routes in ProtectedRoute; /staff, /settings, /integrations require admin.

src/components/Header.tsx — real user/email, role badge, working sign-out.

src/components/AppSidebar.tsx — hide admin-only items (Staff, Settings, Integrations) for non-admins.

Project memory files (repo root)

AGENTS.md — agent operating instructions for this repo.

STATUS.md — current build status (Step 1 in progress / done).

TASKS.md — Step 1 checklist + backlog for Step 2+.

DECISIONS.md — key architectural decisions (Dashboard = main app, external Supabase, roles in user_roles).

CHANGELOG.md — Step 1 entry.

PRODUCT_SPEC.md — concise spec carrying forward the audit findings + roadmap.

Manual owner-promotion step (will be included in the report)

After the first signup, run this once in the Supabase SQL editor to make yourself admin:

INSERT INTO public.user_roles (user_id, role)

SELECT id, 'admin'::public.app_role FROM auth.users WHERE email = 'YOUR_OWNER_EMAIL'

ON CONFLICT (user_id, role) DO NOTHING;

Out of scope (Step 2+)

Public lead intake, n8n/VAPI/Voiceflow webhooks, Stripe, Twilio, Google Calendar, marketing merge, custom domain.

Remaining advisory warnings (require your action in Supabase dashboard)

Reduce Auth OTP expiry to ≤ 1 hour.

Upgrade Postgres to apply latest security patches.

(Optional) Enable "Leaked password protection" in Auth settings.

Approve to switch to build mode and finish Step 1.
```
