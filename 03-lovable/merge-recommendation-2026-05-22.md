# Merge Recommendation

Updated: 2026-05-22

## Recommendation

Make **Dashboard Lovable** the main ClinicPilot X app and port/rebuild the Marketing Lovable pages into it.

## Why

Dashboard Lovable already contains the harder product work:

- Dashboard routes.
- External Supabase connection.
- Tables for appointments, automation logs, integrations, leads, patients, payments, settings, and staff.
- Some modules already querying Supabase.

Marketing Lovable is static and easier to port:

- Public marketing pages.
- Static sections/components.
- No backend/auth/integrations.

## Immediate Blockers In Dashboard Lovable

These must be addressed before any client demo:

1. Permissive RLS policies: all tables currently allow public full access.
2. No auth UI.
3. No protected routes.
4. No roles or role guards.
5. Several pages are mock/hardcoded or local-only.
6. No n8n/webhook endpoints.
7. No GitHub sync/export connected.

## Immediate Plan

1. Pause implementation in Marketing Lovable.
2. Make Dashboard Lovable the primary build target.
3. Fix Supabase security and auth first.
4. Add project memory files inside Dashboard Lovable.
5. Move dashboard from `/` to `/app` or `/dashboard`.
6. Port Marketing Lovable public pages into Dashboard Lovable at `/`, `/features`, `/pricing`, `/contact`, etc.
7. Wire Contact/demo form into the real `leads` table and/or n8n webhook.
8. Add domain only after the main Lovable project is chosen and stable.
