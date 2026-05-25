# Client Pilot Test Data Plan

Updated: 2026-05-25

## Purpose

Create realistic but controlled test data so the Dashboard Lovable app can be tested before using it with a real client.

## Test Email Pattern

Use Gmail plus-addressing from the owner email:

- `donjericho617+sarahjohnson@gmail.com`
- `donjericho617+michaelchen@gmail.com`
- `donjericho617+emmadavis@gmail.com`
- `donjericho617+staff1@gmail.com`
- `donjericho617+clinicclient1@gmail.com`

These should route to the same Gmail inbox while appearing as distinct email addresses to the app.

## Recommended Test Records

### Leads

1. Sarah Johnson
   - Email: `donjericho617+sarahjohnson@gmail.com`
   - Service: Botox / med spa consultation
   - Lead type: credible lead
   - Source: website/email
   - Notes: asks about pricing and next available appointment

2. Michael Chen
   - Email: `donjericho617+michaelchen@gmail.com`
   - Service: dental implant consultation
   - Lead type: credible lead
   - Source: email
   - Notes: asks about cost range and financing

3. Vendor Solicitation
   - Email: `donjericho617+vendor1@gmail.com`
   - Lead type: vendor_or_solicitation
   - Notes: fake marketing vendor pitch

4. Unsure
   - Email: `donjericho617+unsure1@gmail.com`
   - Lead type: unsure
   - Notes: vague message with no clear service intent

### Patients

1. Sarah Johnson
2. Michael Chen

### Appointments

1. Sarah Johnson consultation, future date.
2. Michael Chen consultation, future date.

### Staff

1. Staff test user:
   - Email: `donjericho617+staff1@gmail.com`
   - Role: staff, not admin

## QA Expectations

- Lead records should persist after page refresh.
- Converted leads should appear as patients if conversion exists.
- Appointments should appear in both Appointments and Calendar if linked.
- Staff-only user should not access admin-only routes.
- Demo records should be clearly labeled or removed before client demo.

