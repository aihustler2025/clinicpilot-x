# Dashboard Login and Role Access

Updated: 2026-05-25

## Current Preview URL

- App preview: `https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app/`
- Login page: `https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app/auth`

The project is not published yet, so this is still the Lovable preview URL.

## Admin Access

There is no separate admin login URL at this stage.

Admin users sign in through the same `/auth` page. After login, the app checks Supabase roles and allows admin-only modules.

Current admin account:

- Email: `donjericho617@gmail.com`
- Roles verified in Supabase: `admin`, `staff`
- Password: the password the owner created during app signup. Codex and Lovable cannot read or recover it.

Expected admin-only modules:

- `/staff`
- `/settings`
- `/integrations`

## Staff Access

Staff users also sign in through the same `/auth` page.

A staff-only user should be able to access normal dashboard/staff workflow modules but should not be able to access admin-only modules.

Recommended test staff account pattern:

- `donjericho617+staff1@gmail.com`
- `donjericho617+staff2@gmail.com`

Use a password controlled by the owner. Do not share real passwords in chat.

## Regular User / Client Access

No separate client/customer portal has been verified yet.

Current app language says `Staff sign-in`, so for now the app appears to be staff/admin oriented. If a public client portal is intended, it should be documented and built as a separate future workflow.

## Current Module List To Verify

Visible modules reported by owner:

- Dashboard
- Calendar
- Appointments
- Leads
- Patients
- Staff
- Automation Center
- Voice Assistant
- Payments
- Integrations
- Settings

Profile menu reported by owner:

- Profile
- Settings
- Support
- Logout

## Immediate QA Rule

Codex should verify app behavior directly after owner signs into the in-app browser. Lovable implementation claims remain unverified until Codex checks the preview, Supabase, or repo evidence.

