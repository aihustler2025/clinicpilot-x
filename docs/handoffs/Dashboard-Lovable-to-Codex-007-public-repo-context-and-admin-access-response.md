# Dashboard Lovable → Codex 007 — Public Repo Context & Admin Access Response

_From: Dashboard Lovable_
_To: Codex (PM + QA lead)_
_Date: 2026-05-24_
_Scope: Step 1 only — safe owner/admin access. No Step 2 work._

---

## 0. Extra Context (per latest owner instructions)

### 0.1 Two Lovable Projects

ClinicPilot X currently has **two** Lovable projects:

- **Marketing Lovable** — public marketing website only. **On hold.**
- **Dashboard Lovable** — main app / dashboard / backend. **Primary project going forward.**

**Current decision:** Dashboard Lovable is the main app going forward. Marketing Lovable is on hold and its public pages will likely be ported into Dashboard Lovable later.

Reference files in the shared repo:

- https://github.com/aihustler2025/clinicpilot-x/blob/main/03-lovable/two-lovable-project-strategy.md
- https://github.com/aihustler2025/clinicpilot-x/blob/main/03-lovable/merge-recommendation-2026-05-22.md

### 0.2 Source of Truth

GitHub is the shared source of truth for both Lovable and Codex:

https://github.com/aihustler2025/clinicpilot-x

At the start of every future session, Lovable should read these files before doing any work:

- `AGENTS.md`
- `STATUS.md`
- `TASKS.md`
- `DECISIONS.md`
- `CHANGELOG.md`
- `PRODUCT_SPEC.md`
- `docs/NAMING.md`

### 0.3 Roles

- **Codex** = project manager + QA lead.
- **Lovable** = implementation.
- Lovable implementation claims are **not considered complete** until Codex verifies them against the manual checklist in section 3.

---

## 1. Verification Answers

| Item | Value |
|---|---|
| Preview URL | `https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app` |
| Published URL | Not yet published |
| Supabase project ref | `zglkebeaimtvpynmlrra` |
| Email confirmation toggle | Owner action in Supabase Auth dashboard |
| `auth.users` row count | **0** |
| `public.user_roles` row count | **0** (no admin yet) |

**Email confirmation recommendation:** leave "Confirm email" **ON** in Supabase Auth. If the owner wants a smoother first signup, they may toggle it **OFF** just for the initial owner signup, then turn it back **ON** immediately afterwards. Default = leave ON.

**Safe bootstrap order:**

1. Owner signs up at `/auth` (creates the first `auth.users` row; trigger creates a `profiles` row + temporary `staff` role).
2. Owner runs the promotion SQL (section 2.B) in the Supabase SQL editor to add the `admin` role.
3. Owner signs out and signs back in so the session picks up the new role.
4. Owner runs verification SQL (sections 2.A, 2.C, 2.D).
5. Owner walks through the manual checklist (section 3).

---

## 2. SQL Snippets

All snippets are read-only or idempotent. Run them in the Supabase SQL editor for project `zglkebeaimtvpynmlrra`.

### 2.A — Inspect users and roles

```sql
-- Count and list current auth users
select id, email, created_at, email_confirmed_at
from auth.users
order by created_at desc;

-- Current role assignments
select ur.user_id, u.email, ur.role, ur.id as role_row_id
from public.user_roles ur
left join auth.users u on u.id = ur.user_id
order by u.email, ur.role;
```

### 2.B — Promote owner email to admin (idempotent)

Replace `YOUR_OWNER_EMAIL` with the email the owner used to sign up.

```sql
-- Add the admin role for the owner (safe to re-run)
insert into public.user_roles (user_id, role)
select u.id, 'admin'::public.app_role
from auth.users u
where u.email = 'YOUR_OWNER_EMAIL'
on conflict (user_id, role) do nothing;

-- Optional: remove the auto-assigned temporary 'staff' role for the owner
-- (only run this if you want the owner to be admin-only)
delete from public.user_roles ur
using auth.users u
where ur.user_id = u.id
  and u.email = 'YOUR_OWNER_EMAIL'
  and ur.role = 'staff'::public.app_role;

-- Verify
select u.email, ur.role
from public.user_roles ur
join auth.users u on u.id = ur.user_id
where u.email = 'YOUR_OWNER_EMAIL';
```

### 2.C — Verify no anon / `USING (true)` full-access policies remain

```sql
-- Any policy that targets anon OR uses USING (true) on a public table is a red flag
select schemaname, tablename, policyname, roles, cmd, qual, with_check
from pg_policies
where schemaname = 'public'
  and (
    'anon' = any(roles)
    or qual = 'true'
    or with_check = 'true'
  );
-- Expected: 0 rows

-- Confirm RLS is enabled on every public table
select c.relname as table_name, c.relrowsecurity as rls_enabled
from pg_class c
join pg_namespace n on n.oid = c.relnamespace
where n.nspname = 'public' and c.relkind = 'r'
order by c.relname;
-- Expected: rls_enabled = true on every row
```

### 2.D — Verify `has_role()` and `is_staff()` exist and are SECURITY DEFINER

```sql
select n.nspname as schema,
       p.proname as function_name,
       p.prosecdef as security_definer,
       pg_get_function_identity_arguments(p.oid) as args
from pg_proc p
join pg_namespace n on n.oid = p.pronamespace
where n.nspname = 'public'
  and p.proname in ('has_role', 'is_staff')
order by p.proname;
-- Expected: both functions present, security_definer = true

-- Sanity check (replace with owner uid after signup)
-- select public.has_role('OWNER_UUID'::uuid, 'admin'::public.app_role);
-- select public.is_staff('OWNER_UUID'::uuid);
```

---

## 3. Manual Verification Checklist

Run in the preview URL after the owner has been promoted to `admin`.

1. **Anon redirect** — Open the preview in a private window. Any protected route (e.g. `/`, `/patients`, `/staff`) redirects to `/auth`.
2. **Owner sign-in** — Owner signs in with the promoted email and lands inside the dashboard.
3. **Admin-only routes** — Owner can open `/staff`, `/settings`, and `/integrations` without being redirected.
4. **Non-admin block** — Sign up a second test account (auto-gets `staff` role). Confirm it is redirected to `/unauthorized` when trying to open `/staff`, `/settings`, or `/integrations`.
5. **Sign-out** — The header sign-out button clears the session and returns to `/auth`.
6. **Header identity** — Header shows the real signed-in email and a role badge (e.g. `admin`).
7. **No anon data leak** — From an anonymous session (no JWT), direct REST calls to any operational table return `[]` or `401`. Tables to spot-check: `profiles`, `user_roles`, `patients`, `appointments`, `leads`, `payments`, `staff`, `integrations`, and any automation/log tables.

---

## 4. Out of Scope (explicitly NOT done in this handoff)

- Step 2 work of any kind
- n8n connection
- Domain / DNS setup
- Merging marketing pages into Dashboard Lovable
- Stripe, Twilio, VAPI, Voiceflow, Google Calendar
- Payment flows
- Public lead capture / public-facing edge functions
- Any new RLS policies, table changes, or code changes

---

## 5. Awaiting From Codex

Please confirm that **Step 1 passes the full checklist in section 3** before Dashboard Lovable begins Step 2. If any item fails, file the failing item back to Lovable with the route, the action taken, and the observed vs. expected behaviour.
