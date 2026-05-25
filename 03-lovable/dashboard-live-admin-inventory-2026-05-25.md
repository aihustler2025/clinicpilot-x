# Dashboard Live Admin Inventory

Date: 2026-05-25

Preview tested:

- `https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app/`

Account:

- `donjericho617@gmail.com`
- Role badge shown in header: `admin`

## Result Summary

The owner account is logged in and admin access is working at the route level. All major sidebar modules loaded without redirecting to `/auth` or `/unauthorized`.

This does not mean every feature is real or production-ready. The first pass shows many modules are still using demo/static-looking records and placeholder integration states.

## Sidebar Modules Checked

- Dashboard: loaded
- Calendar: loaded
- Appointments: loaded
- Leads: loaded
- Patients: loaded
- Staff: loaded
- Automation Center: loaded
- Voice Assistant: loaded
- Payments: loaded
- Integrations: loaded
- Settings: loaded

## Profile Menu Checked

Profile menu button label:

- `AI Hustler`

Menu shows:

- `donjericho617@gmail.com`
- Profile
- Settings
- Support
- Log out

## Observations

### Dashboard

Dashboard loads with overview metrics, quick actions, recent alerts, and today's schedule.

Observed sample metrics:

- Today's Appointments: `24`
- New Leads: `8`
- Payments Collected: `$3,247`
- Pending Follow-ups: `12`

Likely issue: data looks demo/static until proven otherwise.

### Calendar

Calendar loads May 2026, with visible appointment items on May 25. It also shows a calendar integration callout.

Observed callout:

- Calendar Integration
- Connect Google Calendar, Calendly, or other scheduling tools for seamless sync
- Connect Now

Likely issue: integration flow needs verification; may be placeholder.

### Appointments

Appointments loads table/list UI with filters.

Observed sample data includes 2024 dates and cosmetic service examples, which likely indicates seed/demo data.

### Leads

Leads loads with source/status filters and a lead table.

Observed summary:

- Total Leads: `8`
- New Today: `4`
- Chatbot: `2`
- Manual: `2`
- Messenger: `2`
- WhatsApp: `2`

Likely issue: records may be static/mock until create/update/persistence is tested.

### Patients

Patients loads with Add Patient button, filters, and patient records.

Observed summary:

- Total Patients: `5`
- New Patients This Month: `2`
- Repeat Patients: `1`

Likely issue: records may be static/mock until create/update/persistence is tested.

### Staff

Staff loads for admin with Add Staff Member button, filters, and staff records.

Observed summary:

- Total Staff: `5`
- Active Staff: `3`
- On Leave: `1`

This confirms admin route access for the owner account.

### Automation Center

Automation Center loads workflow cards and toggles.

Observed workflows include:

- Lead Capture Automation
- Appointment Confirmation
- Payment Reminders
- AI Follow-up Calls
- Chatbot Routing Rules

Likely issue: workflow cards may be UI-only until n8n/Make/webhook connections are verified.

### Voice Assistant

Voice Assistant loads call metrics, call log, and campaign tabs.

Observed sample metrics:

- Total Calls Today: `47`
- Successful Calls: `38`
- Missed/Failed: `9`
- Avg Call Duration: `6:32`

Likely issue: voice call data appears demo/static until provider integration is verified.

### Payments

Payments loads records, filters, and New Payment button.

Observed sample metrics:

- Total Collected This Month: `$22,800`
- Pending Invoices: `2`
- Overdue Payments: `1`

Do not run real payment tests until Stripe/payment mode is confirmed.

### Integrations

Integrations loads and reports 3 of 6 integrations connected.

Observed integration states:

- Google Calendar: connected
- Calendly: disconnected
- Stripe: connected
- Twilio SMS: disconnected
- Gmail: connected
- Zoom: disconnected

Important contradiction: page also says `Backend Integration Required` and offers `Connect Supabase`, even though Supabase is already connected and in use. This should be sent to Lovable as a likely stale placeholder.

### Settings

Settings loads account, notification, clinic, and automation settings.

Observed profile values are not the real owner account:

- Full Name: `Dr. Sarah Johnson`
- Email Address: `sarah.johnson@clinic.com`
- Clinic Name: `Advanced Cosmetic Surgery Center`

Important issue: Settings page is showing demo profile/clinic data instead of the logged-in owner/clinic state. This should be corrected before client demo.

## Priority Issues For Lovable

1. Settings page shows demo account data instead of `donjericho617@gmail.com` / real clinic owner profile.
2. Integrations page still says `Backend Integration Required` / `Connect Supabase` even though Supabase auth and roles are active.
3. Many modules show 2024 dates and sample records; Lovable must clarify which are mock UI vs Supabase-backed data.
4. Automation, voice, payments, and integration statuses must be marked as placeholder unless real providers are connected.

## Next QA Step

Run functional tests:

1. Create a test lead and verify persistence after refresh.
2. Create a test patient and verify persistence after refresh.
3. Create a test appointment and verify it appears in Appointments and Calendar.
4. Check whether Quick Actions open working modals or dead UI.
5. Create a staff-only account and verify admin-only route blocking.

