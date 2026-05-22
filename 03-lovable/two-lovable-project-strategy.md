# Two Lovable Project Strategy

Updated: 2026-05-22

## Situation

ClinicPilot X currently appears to have two separate Lovable projects:

1. **Marketing Lovable**
   - Known project URL: `https://lovable.dev/projects/37666967-bc8e-4032-9043-f45713e2bc22`
   - Audit result: static marketing site only.
   - No dashboard, backend, auth, database, n8n, Supabase, or Lovable Cloud connected.

2. **Dashboard Lovable**
   - Project URL/ID: pending from owner.
   - Owner says this project contains the user dashboard, admin dashboard, and backend-related work.

## Working Names

Use these labels until final consolidation:

- `Marketing Lovable` = public website project.
- `Dashboard Lovable` = app/dashboard/backend project.

## Options

### Option A - Dashboard Lovable Becomes The Main App

Use Dashboard Lovable as the primary project and copy/rebuild the marketing pages into it.

Pros:

- Fastest route if Dashboard Lovable already has auth, backend, and app structure.
- One domain/app to deploy.
- Easier routing: marketing pages plus `/dashboard`.
- Easier future maintenance.

Cons:

- Marketing site may need to be copied/rebuilt.
- Visual polish from Marketing Lovable must be preserved manually.

Recommended if Dashboard Lovable already has real backend/auth/dashboard work.

### Option B - Keep Projects Separate

Use Marketing Lovable for `clinicpilotx.com` and Dashboard Lovable for `app.clinicpilotx.com` or `portal.clinicpilotx.com`.

Pros:

- Least merge work initially.
- Marketing and app can deploy independently.
- If both projects are mature, this avoids a risky merge.

Cons:

- More DNS/deployment complexity.
- More places for Lovable/project memory to drift.
- Harder to keep branding/components aligned.
- Login/signup handoff must be wired cleanly.

Recommended only if both projects are already strong and merge would slow launch.

### Option C - Marketing Lovable Becomes Main App

Use Marketing Lovable as the primary project and build dashboard/backend into it.

Pros:

- Keeps existing public website intact.
- Straightforward if Dashboard Lovable is weak or mostly mockup.

Cons:

- Current Marketing Lovable has no backend/auth/dashboard.
- Could waste existing Dashboard Lovable work.
- Slower if dashboard/backend already exists elsewhere.

Not recommended until Dashboard Lovable is audited.

## Current Recommendation

Audit Dashboard Lovable next before approving implementation in Marketing Lovable.

Most likely best path:

1. Make Dashboard Lovable the main product/app if it has real auth/backend/dashboard work.
2. Move or recreate the marketing pages inside Dashboard Lovable.
3. Use one primary domain: `clinicpilotx.com`.
4. Route public pages at `/`, `/features`, `/pricing`, `/contact`.
5. Route product area at `/dashboard`.

Fallback path:

- Keep Marketing Lovable on `clinicpilotx.com`.
- Put Dashboard Lovable on `app.clinicpilotx.com`.

## Do Not Do Yet

- Do not approve backend creation in Marketing Lovable until Dashboard Lovable is audited.
- Do not connect DNS until the final Lovable project/domain architecture is chosen.
- Do not connect n8n until we know which Lovable project owns the app/backend.
