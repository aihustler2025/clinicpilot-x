# Dashboard Handoff 008 Verification

Date: 2026-05-25

Preview verified:

- `https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app`

Account:

- `donjericho617@gmail.com`
- Admin session active

## Verdict

Handoff 008 is verified as complete for its approved scope.

## Verified

- Dashboard route loads and shows `Demo data` badge.
- Settings route loads and shows real account email `donjericho617@gmail.com`.
- Settings no longer shows fake owner values such as `sarah.johnson@clinic.com` or `Advanced Cosmetic Surgery Center`.
- Profile route loads and shows real account email `donjericho617@gmail.com`.
- Profile no longer shows fake owner values.
- Integrations route no longer shows `Backend Integration Required` or `Connect Supabase`.
- Integrations reports `0 of 6 integrations connected`.
- Provider tiles show `Not connected`.
- Demo badges appear on:
  - Dashboard
  - Calendar
  - Appointments
  - Leads
  - Patients
  - Staff
  - Automation Center
  - Voice Assistant
  - Payments

## Notes

The Staff page still includes sample staff names, including Dr. Sarah Johnson, but the page is now visibly marked as `Demo data`. This is acceptable for handoff 008 because the approved scope was to make demo data honest, not to wire CRUD or replace all sample records.

Integrations contains the phrase `0 Connected` as a count label, but no provider tile is marked as connected. This is acceptable.

## Remaining Work

Next functional QA should test actual persistence:

1. Lead create/update/persistence.
2. Patient create/update/persistence.
3. Appointment create/update/persistence and Calendar sync.
4. Staff-only account creation and admin route blocking.
5. Real n8n/email intake integration strategy.

