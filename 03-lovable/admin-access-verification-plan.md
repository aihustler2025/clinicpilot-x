# Admin Access Verification Plan

Updated: 2026-05-24

## Current State

Dashboard Lovable responded to handoff 007.

Response saved at:

`docs/handoffs/Dashboard-Lovable-to-Codex-007-public-repo-context-and-admin-access-response.md`

Key facts:

- Preview URL: `https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app`
- Supabase project ref: `zglkebeaimtvpynmlrra`
- `auth.users`: 0 rows
- `public.user_roles`: 0 rows
- No admin account exists yet

## Decision

No custom reply to Lovable is needed yet.

Next action is owner/admin account setup and verification.

## Owner/Admin Setup

1. Open the Dashboard Lovable preview `/auth`.
2. Sign up with the owner-controlled email and a strong password.
3. Confirm email if Supabase email confirmation is enabled.
4. In Supabase SQL editor, promote that email to admin.
5. Sign out and sign back in.
6. Run the manual verification checklist.

## SQL To Promote Owner

Replace `YOUR_OWNER_EMAIL` with the owner signup email.

```sql
insert into public.user_roles (user_id, role)
select u.id, 'admin'::public.app_role
from auth.users u
where u.email = 'YOUR_OWNER_EMAIL'
on conflict (user_id, role) do nothing;
```

## Verify Roles

```sql
select ur.user_id, u.email, ur.role
from public.user_roles ur
left join auth.users u on u.id = ur.user_id
order by u.email, ur.role;
```

## Verify No Public Full Access

```sql
select schemaname, tablename, policyname, roles, cmd, qual, with_check
from pg_policies
where schemaname = 'public'
  and (
    'anon' = any(roles)
    or qual = 'true'
    or with_check = 'true'
  );
```

Expected: 0 rows.

## Manual Checklist

- Signed-out visitor hitting `/`, `/patients`, or `/staff` redirects to `/auth`.
- Owner/admin can sign in.
- Admin can access `/staff`, `/settings`, and `/integrations`.
- Non-admin staff is blocked from `/staff`, `/settings`, and `/integrations`.
- Sign-out works.
- Header shows real signed-in email and role badge.
- Anonymous REST calls do not leak operational table rows.
