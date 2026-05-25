# Supabase and Lovable Cloud Cost Audit

Updated: 2026-05-25

## Current Finding

Dashboard Lovable is currently connected to an external Supabase project:

- Supabase project ref: `zglkebeaimtvpynmlrra`
- Supabase organization seen by owner: `Bazooka`
- Relevant project name seen by owner: `Prime Clinic Pilot`
- Owner app account email: `donjericho617@gmail.com`

This project is not confirmed to be on Lovable Cloud. Previous Dashboard Lovable responses described it as a standalone Supabase backend.

## Account Billing Findings

Checked in Supabase dashboard on 2026-05-25:

- Organization: `Buzzooka`
- Plan shown in Supabase UI: `Pro Plan`
- Spend cap: enabled
- Current billing cycle: 2026-05-08 to 2026-06-08
- Supabase UI says the organization has not exceeded Pro Plan quota in the current cycle.
- Projects shown:
  - `clinicpilot` / ref `zglkebeaimtvpynmlrra` / AWS ap-southeast-1 / `micro`
  - `Prime10XSocialFi` / ref `lehgbboxkgagjmbqkacl` / AWS ap-southeast-2 / `nano`
  - `Video Muse` / ref `xoxnuutqkqxnhogxzglh` / paused
- Recent paid invoices shown:
  - 2026-05-08: `$34.35`
  - 2026-04-08: `$35.00`
  - 2026-03-08: `$33.06`
  - 2026-02-08: `$35.00`
  - 2026-01-08: `$34.17`

Interpretation: this Supabase organization is costing money already. The ClinicPilot project is not free under the current organization plan.

## Official Pricing Notes To Verify In Account

- Supabase Free plan allows 2 active projects and pauses free projects after inactivity.
- Supabase Pro starts at $25/month and includes the first project.
- Supabase additional projects on paid plans start from $10/month.
- Lovable Cloud includes backend features such as database, auth, storage, and edge functions.
- Lovable Cloud usage is separate from the Lovable subscription. Lovable currently documents included monthly usage, but usage above that allowance can cost extra.
- Lovable documentation currently says migration from an existing Supabase-connected project to Lovable Cloud is not supported; existing Supabase integrations continue to work.

## Cost Question

The open question is whether the `Bazooka` Supabase organization is on Free or Pro.

If the organization is on Free and has no more than 2 active projects, the active Supabase projects may be $0/month.

If the organization is on Pro, the base charge is expected to start at $25/month, with possible additional project/compute charges depending on active projects and settings.

## Recommendation

Do not migrate or rebuild the backend today just to chase savings. Lovable currently documents that moving an existing Supabase-connected app into Lovable Cloud is not supported as a direct migration path, so a switch would likely mean a rebuild or careful manual migration.

First:

1. Promote `donjericho617@gmail.com` to admin.
2. Verify Dashboard Lovable Step 1 auth and RLS.
3. Open Supabase Billing for the `Bazooka` organization and record the actual plan/charges.
4. Open Lovable Settings > Cloud & AI balance and record whether this project has Lovable Cloud usage or allowance available.
5. Decide whether to keep Supabase or rebuild/new-build on Lovable Cloud after the app is accessible.

## Admin Promotion SQL

Completed on 2026-05-25 in the Supabase SQL editor for project `zglkebeaimtvpynmlrra`:

```sql
insert into public.user_roles (user_id, role)
select u.id, 'admin'::public.app_role
from auth.users u
where u.email = 'donjericho617@gmail.com'
on conflict (user_id, role) do nothing;
```

Then verify:

```sql
select ur.user_id, u.email, ur.role
from public.user_roles ur
left join auth.users u on u.id = ur.user_id
where u.email = 'donjericho617@gmail.com'
order by u.email, ur.role;
```

After this succeeds, sign out of the ClinicPilot X preview and sign back in so the app refreshes the user role.

## Admin Promotion Result

Verification query returned:

- `donjericho617@gmail.com` / `admin`
- `donjericho617@gmail.com` / `staff`

This means the owner account now has both staff and admin roles. App-side verification still requires signing into the preview with the owner password.

## RLS Quick Verification

The public-policy check returned `0 rows` on 2026-05-25:

```sql
select schemaname, tablename, policyname, roles, cmd, qual, with_check
from pg_policies
where schemaname = 'public'
  and (
    'anon' = any(roles)
    or 'public' = any(roles)
    or qual = 'true'
    or with_check = 'true'
  )
order by tablename, policyname;
```

This verifies that the previous broad public/anon full-access policy pattern is not present for this specific check.
