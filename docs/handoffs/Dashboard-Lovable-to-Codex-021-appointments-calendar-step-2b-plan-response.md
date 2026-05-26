# Dashboard Lovable to Codex 021: Appointments and Calendar Step 2B Plan Response

Date received: 2026-05-26

Source:

- Owner pasted/attached Dashboard Lovable response as `C:\Users\Rosstafari\Downloads\DASHBOARD LOVABLE TO CODEX 14.docx`.

## Summary From Lovable

Dashboard Lovable responded to handoff 021 with a Step 2B plan for Appointments and Calendar.

The plan states:

- `/appointments` is currently 100% mock/local-state UI.
- `/calendar` is currently 100% mock UI.
- The `appointments` Supabase table exists with RLS but is bare.
- Proposed build mirrors the proven `useLeads` pattern.
- Proposed MVP includes real Supabase CRUD, appointment detail drawer, month calendar, day agenda, and deterministic rule-based PriorityBook.
- External integrations remain `Not connected`.

## Proposed New Files

- `src/hooks/useAppointments.ts`
- `src/lib/priority.ts`
- `src/lib/appointmentStatuses.ts`
- `src/components/appointments/AppointmentFormDialog.tsx`
- `src/components/appointments/AppointmentDetailDrawer.tsx`
- `src/components/appointments/AppointmentStatusBadge.tsx`
- `src/components/calendar/MonthCalendar.tsx`
- `src/components/calendar/DayAgenda.tsx`

## Proposed Edited Files

- `src/pages/Appointments.tsx`
- `src/pages/CalendarView.tsx`
- `src/components/dashboard/CalendarWidget.tsx`
- `src/components/dashboard/QuickActions.tsx`

## Proposed Migration

Additive only:

- `updated_at`
- `duration_minutes`
- `provider_id`
- `lead_id`
- `source`
- `location`
- `meeting_link`
- `external_calendar_id`
- `request_type`
- `priority_score`
- `priority_label`
- `priority_reason`
- indexes for scheduled date/status/provider/patient/lead

No broad RLS changes proposed.

## Key Product Decisions Needed

Lovable asked:

1. Confirm live status enum values before migration.
2. Confirm whether `request_type='request'` items appear in `/appointments`, `/calendar`, or both.
3. Confirm provider source.
4. Confirm PriorityBook high-ticket service list.
5. Confirm DemoDataBadge removal timing.

Codex response is captured in handoff 022.

