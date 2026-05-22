# Marketing and Dashboard Lovable Responses 2

Source: `C:/Users/Rosstafari/Downloads/MARKETING & DASHBOARD LOVABLE TO CODEX 2.docx`

```text
MARKETING & DASHBOARD LOVABLE TO CODEX 2

MARKETING LOVABLE TO CODEX 2

Noted. Here's what I have recorded and ready for you:

Hold status confirmed:

This project = Marketing Lovable only (public website, no backend/auth/dashboard)

No code, DNS, domain, backend, or automation work will be done here

clinicpilotx.com remains unconnected until you decide merge vs. separate

Contact form stays mock/toast-only unless you later request a lightweight form endpoint

Audit artifacts ready to provide on request:

Exact file/component copy list — every page, section component, shared component, hook, and UI primitive that would need to move into Dashboard Lovable

Route list — all 9 public routes with their file paths

Design tokens — full CSS variable list from index.css, Tailwind config mappings, custom gradients, shadows, radius, and animation tokens

Assets / public files — placeholder.svg, robots.txt, logo/favicon paths in index.html

Known marketing blockers — dead checkout anchor, placeholder videos, mock forms, missing Privacy/Terms/HIPAA pages, placeholder WhatsApp number, placeholder Google Calendar link, placeholder YouTube IDs

When you're ready to port pages into Dashboard Lovable (or if you decide to keep them separate and just polish this site), let me know and I'll deliver the exact copy checklist and any fixes you want applied.

DASHBOARD LOVABLE TO CODEX

Step 1 Plan — Security, Auth, Roles, Project Memory

Scope: lock down the Supabase backend, add real authentication and roles, and document the project's security posture. No marketing merge, no domains, no n8n/Stripe/Twilio/VAPI. No code is written until you approve this plan.

1. Project memory files to create / update

These are persistent project-level memory entries (managed via the Memory tool / Knowledge tab), not source files:

security-memory (via security--update_memory) — describes access model, what must never happen, and accepted risks. Initial content:

Internal CRM for clinic staff; not public.

All public.* tables require an authenticated session.

Patient PII, payments, automation logs must never be readable by anon.

Only admin may write to settings, integrations, staff, user_roles.

Service-role key must never reach the frontend.

project/architecture — Dashboard Lovable is the main app, external Supabase zglkebeaimtvpynmlrra, no Lovable Cloud, no edge functions yet.

project/auth-model — Supabase email/password auth, profiles table mirrors auth.users, roles live in user_roles (enum: admin, doctor, staff, receptionist), checked via has_role() SECURITY DEFINER.

project/data-status — per-page list of real-vs-mock data sources, to be replaced in Step 2.

project/roadmap — Step 1 = security/auth; Step 2 = replace mocks; Step 3 = marketing merge; Step 4 = webhooks/integrations.

2. Database changes (one migration, awaiting your approval)

New objects:

public.app_role enum: admin, doctor, staff, receptionist.

public.profiles — one row per auth user. Fields: user_id (FK auth.users ON DELETE CASCADE, UNIQUE), full_name, email, avatar_url, phone, timestamps.

public.user_roles — user_id (FK auth.users ON DELETE CASCADE), role app_role, UNIQUE(user_id, role).

public.has_role(_user_id uuid, _role app_role) returns boolean — SECURITY DEFINER, set search_path = public, reads user_roles. Prevents recursive RLS.

public.is_staff(_user_id uuid) returns boolean — convenience wrapper: true if user has any of admin/doctor/staff/receptionist.

public.handle_new_user() trigger on auth.users AFTER INSERT → inserts a profiles row, and inserts a default staff role for the first signed-up user only if user_roles is empty (so the seed admin can be promoted manually). All other signups get no role until an admin grants one.

public.update_updated_at_column() trigger function; add updated_at columns + triggers to profiles, user_roles, and existing tables that lack them (non-breaking).

Existing tables: no column changes in Step 1 (to avoid breaking current pages). Only RLS policies are rewritten.

Out of scope for Step 1 (flagged for Step 2): adding owner_user_id / created_by columns to patients, appointments, leads, payments so per-user ownership policies become possible.

3. RLS policy plan — per table

For every table below, the existing "Allow full access (testing)" policy is dropped first. RLS stays enabled.

Table

SELECT

INSERT

UPDATE

DELETE

profiles

own row OR has_role(uid,'admin')

own row only (user_id = auth.uid())

own row OR admin

admin only

user_roles

own rows OR admin

admin only

admin only

admin only

patients

any staff (is_staff(uid))

any staff

any staff

admin only

appointments

any staff

any staff

any staff

admin only

leads

any staff

any staff

any staff

admin only

payments

any staff

admin only

admin only

admin only

staff

any staff

admin only

admin only

admin only

settings

any staff

admin only

admin only

admin only

integrations

any staff

admin only

admin only

admin only

automation_logs

any staff

any staff (logs are inserts)

admin only

admin only

Notes:

All policies are TO authenticated (anon role gets nothing).

No policy references its own table in its USING clause — all role checks go through has_role() / is_staff() SECURITY DEFINER to avoid infinite recursion.

Per-row ownership (e.g., "doctor sees only their patients") is deferred to Step 2 after owner_user_id columns exist.

4. Auth routes and protected-route wrapper

New routes in src/App.tsx:

/auth — combined sign-in / sign-up (email + password). Public.

/auth/forgot-password — sends reset email with redirectTo: ${origin}/auth/reset-password. Public.

/auth/reset-password — handles type=recovery, calls supabase.auth.updateUser({ password }). Public.

/unauthorized — shown when an authenticated user lacks the required role. Public to authenticated users.

All existing app routes (/, /calendar, /appointments, /leads, /patients, /staff, /automation, /voice-assistant, /payments, /integrations, /settings, /profile) become protected.

New wrappers:

<AuthProvider> (context) — wraps app; subscribes to supabase.auth.onAuthStateChange BEFORE calling getSession(); exposes user, session, roles, loading, signOut.

<ProtectedRoute requireRole?> — redirects unauthenticated users to /auth, redirects authenticated-but-unauthorized users to /unauthorized. Defers render until loading is false to prevent flicker.

Admin-only routes initially: /staff, /settings, /integrations. All others require any staff role.

Header gets a sign-out button and shows the user's email + role badge.

5. Role model

Enum app_role: admin, doctor, staff, receptionist.

admin — full app access; only role that can write settings, integrations, staff, user_roles, and delete records.

doctor — read/write patients, appointments, leads, automation_logs; read payments.

staff / receptionist — same as doctor in Step 1 (we'll narrow later if you want a tighter split).

A user can hold multiple roles (table is UNIQUE on (user_id, role)).

Bootstrap: first signed-up account is seeded with staff; you (the owner) then run a one-line insert via SQL editor to grant yourself admin. Instructions provided in the chat after migration.

6. Files / components expected to touch

New files:

src/contexts/AuthContext.tsx

src/hooks/useAuth.ts, src/hooks/useRoles.ts

src/components/ProtectedRoute.tsx

src/components/RoleBadge.tsx

src/pages/auth/SignIn.tsx

src/pages/auth/ForgotPassword.tsx

src/pages/auth/ResetPassword.tsx

src/pages/Unauthorized.tsx

Edited files:

src/App.tsx — wrap with AuthProvider, add auth routes, wrap app routes in ProtectedRoute.

src/components/Header.tsx — user menu, sign-out, role badge.

src/components/AppSidebar.tsx — hide admin-only items for non-admins.

src/pages/Profile.tsx — bind to profiles row (read/update own).

src/pages/Settings.tsx — bind to settings row (admin write only).

Unchanged in Step 1 (mock data stays until Step 2): Dashboard, CalendarView, Automation, Integrations page contents.

7. Safety checks

Migration is wrapped so existing rows survive (no destructive DROP TABLE).

The "Allow full access (testing)" policies are dropped only after the replacement policies are created in the same migration, so the table is never momentarily open.

All RLS policies are scoped TO authenticated — even with the anon key leaked in the bundle, anon cannot read anything.

has_role() is SECURITY DEFINER with fixed search_path = public (prevents search_path hijacking).

No auth.users modifications beyond an AFTER INSERT trigger.

Service-role key stays server-side only; frontend continues to use the publishable anon key.

Supabase linter is run after the migration; any new warnings are addressed before Step 1 is closed.

Auth settings checklist surfaced to you: enable "Leaked password protection (HIBP)", set Site URL and redirect allow-list, decide whether to require email confirmation (recommended ON for production, OFF only during initial seeding).

8. Testing plan

Manual (in preview):

Visit / while signed out → redirected to /auth.

Sign up with owner@clinic.test → profile row auto-created, default staff role assigned.

Promote that user to admin via SQL editor; sign out / in; admin-only sidebar items appear.

Sign up a second user recept@clinic.test → gets no role by default → / redirects to /unauthorized until admin grants receptionist.

As receptionist: can list patients, create appointments, cannot open /settings or /integrations, cannot delete a patient.

Forgot-password flow end-to-end: receives email, lands on /auth/reset-password, sets new password, can sign in.

Sign out, hit /patients directly → redirected to /auth.

Database (via SQL editor or read_query):

select * from public.patients using anon key returns 0 rows.

select public.has_role(auth.uid(),'admin') returns expected boolean per session.

Confirm no policy uses USING (true) anywhere in public.

Automated checks:

Run supabase--linter after migration; expect zero ERROR-level findings.

Run security--run_security_scan; resolve any new findings or document in security-memory.

Exit criteria for Step 1:

All 8 existing tables + 2 new tables have role-scoped RLS, no public access.

Auth pages work; protected routes enforce auth + role.

has_role() and is_staff() functions exist and are used by policies.

Owner account holds admin; at least one non-admin test account verified.

Security memory + project memory files saved.

Awaiting your approval before running the migration or writing any code.
```
