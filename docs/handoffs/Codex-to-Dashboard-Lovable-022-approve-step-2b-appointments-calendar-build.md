# Codex to Dashboard Lovable 022: Approve Step 2B Appointments and Calendar Build

Mode: Build

Action requested: Proceed with the Step 2B Appointments and Calendar build, using the decisions and guardrails below.

## Context

Codex reviewed Dashboard Lovable's response to handoff 021.

The plan is approved with the decisions below.

## Decisions For Blocking Questions

### 1. Status enum values

Approved: read the live enum values via Supabase at the start of build and make the migration safe/additive.

Do not assume enum values blindly. Use `ALTER TYPE ... ADD VALUE IF NOT EXISTS` or the safest equivalent supported by the migration environment.

Canonical statuses we want available:

- `requested`
- `confirmed`
- `completed`
- `cancelled`
- `no_show`
- `rescheduled`

Keep any existing values to avoid breaking rows.

### 2. Appointment requests visibility

Approved default:

- `request_type='request'` appears in both `/appointments` and `/calendar`.
- In `/calendar`, requests should be visually different/muted until confirmed.
- Add filters so staff can show:
  - all
  - requests only
  - confirmed appointments only
  - completed/cancelled/no-show where relevant

This supports the owner's clinic workflow: many inbound bookings are requests first, not final confirmed appointments.

### 3. Provider source

Approved default:

- Use the existing `staff` table for provider picker/source.
- Do not create a new provider model yet.
- If `staff` has insufficient fields, keep the picker flexible and document any follow-up need.

### 4. PriorityBook high-ticket service list

Approved to implement as a simple editable config in `src/lib/priority.ts`.

Initial high-value service terms:

- rhinoplasty
- facelift
- breast augmentation
- breast lift
- tummy tuck
- mommy makeover
- liposuction
- body contouring
- hair transplant
- dental implants
- full arch implants
- veneers
- smile makeover
- invisalign
- orthodontics
- wisdom teeth
- oral surgery
- laser resurfacing
- skin tightening
- weight loss package
- med spa package

Treat Botox/filler inquiries as normal or medium by default unless paired with package language, urgent timing, multiple services, or strong booking intent.

Keep this deterministic and explainable. No AI scoring dependency yet.

### 5. DemoDataBadge timing

Approved default:

- Remove `DemoDataBadge` from `/appointments` and `/calendar` once those pages are reading/writing real Supabase data.
- Keep or clearly label any dashboard widget as demo/limited until the dashboard widget is verified against real appointments.
- Do not leave a page looking like demo data once it is real, because that confuses QA and sales demos.

## Build Approval

Proceed with the proposed files and additive migration.

Build:

- Real Supabase-backed appointments CRUD.
- Appointment/request create and edit dialog.
- Remount-safe modal/draft persistence pattern copied from the fixed Leads implementation.
- Appointment detail drawer.
- Status badge and allowed status transitions.
- Month calendar + selected-day agenda.
- Dashboard calendar widget reading real data if feasible.
- Quick Actions `New Appointment` wired to the real appointment dialog.
- Rule-based PriorityBook fields and display.

## Drag And Drop

Do not implement drag-and-drop rescheduling in Step 2B.

The owner wants draggable calendar behavior eventually, but Codex agrees with deferring it because safe drag/drop needs confirmation, conflict checks, and careful QA.

For Step 2B, rescheduling should happen through edit/detail drawer date/time fields.

## External Integrations

Keep these out of scope and visibly `Not connected`:

- Google Calendar OAuth/sync
- Calendly API/webhooks
- Google Meet automatic creation
- Zoom automatic creation
- Stripe/deposit enforcement
- Twilio/SMS reminders
- VAPI voice
- n8n workflows
- chatbot booking automation

Allowed:

- Store a manually pasted virtual meeting link.
- Add future-proof fields such as `external_calendar_id`.

## Guardrails

Do not:

- Break existing Leads module.
- Change auth/RLS broadly.
- Seed fake production data.
- Claim any integration is connected without proof.
- Start payment/reminder automation.
- Implement broad PMS/practice-management integrations.

## Verification Required

After build, report:

1. Migration summary and before/after appointment row count.
2. Files changed.
3. Whether `/appointments` uses real Supabase data.
4. Whether `/calendar` uses real Supabase data.
5. Create/edit/status/reschedule persistence results.
6. Calendar click/detail behavior.
7. PriorityBook scoring sanity examples.
8. Dashboard widget behavior.
9. Any remaining demo labels.
10. Any blocked tests.

Codex will verify live preview before Step 2B is considered complete.

