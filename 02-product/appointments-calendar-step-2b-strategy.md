# Appointments and Calendar Step 2B Strategy

Updated: 2026-05-26

## Goal

Build ClinicPilot X's internal appointments and calendar workflow so clinics can manage booking requests, confirmed appointments, reschedules, staff/provider assignment, virtual visit links, and high-value lead prioritization before external calendar integrations are activated.

## Product Direction

ClinicPilot X should not start by trying to replace every clinic's existing practice management system. Dental clinics, plastic surgery clinics, med spas, and medical offices often already use a scheduling system inside their practice management software.

The MVP should become the smart front-desk layer:

- Capture appointment requests from leads, chatbot, website forms, email, phone, and manual staff entry.
- Let staff review, approve, reschedule, or decline requests.
- Show requests and confirmed appointments clearly on the internal calendar.
- Help staff prioritize high-value, urgent, or ready-to-book opportunities.
- Prepare for Google Calendar, Calendly, and future practice-management integrations without requiring them on day one.

## Important Booking Principle

For clinics, many patient requests should be treated as appointment requests first, not final confirmed bookings.

Reasons:

- Providers may already be booked.
- Some services require specific rooms, staff, equipment, or longer preparation time.
- Surgical/cosmetic procedures may involve consultations, deposits, pre-screening, and follow-up.
- Clinics often want front-desk or scheduling staff to approve requests manually.

Default MVP behavior:

- A lead can request a time.
- Staff can convert the request into an appointment.
- Appointment status starts as `Requested` or `Pending Review`.
- Staff can approve/confirm after checking schedule and provider availability.

## MVP Data Model

Appointments should support:

- Patient or lead link.
- Full name, email, phone fallback fields.
- Service requested.
- Provider/staff assignment.
- Appointment status.
- Appointment type: in-person, virtual, phone, consultation, procedure.
- Requested date/time.
- Confirmed scheduled start/end.
- Time zone.
- Location or room.
- Virtual meeting link.
- Source: manual, lead, chatbot, contact form, email, phone, Calendly, Google Calendar, API/webhook.
- Priority score.
- Priority label: low, normal, high, urgent/VIP.
- Notes.
- Internal staff notes.
- External calendar/provider IDs for later sync.

Recommended statuses:

- `requested`
- `pending_review`
- `confirmed`
- `reschedule_requested`
- `completed`
- `cancelled`
- `no_show`

## Calendar UX

The internal calendar should feel polished and operational, not like placeholder demo data.

Expected MVP views:

- Month view for overview.
- Week view for staff scheduling.
- Day view for today's clinic flow.
- Agenda/list view for quick scanning.

Expected interactions:

- Click a calendar item to see appointment/request details.
- Create appointment/request from a calendar date/time.
- Drag confirmed appointments or requests to a new date/time if the UI library supports it safely.
- If drag/drop is implemented, show confirmation before saving the new date/time.
- Color-code by status and/or priority.
- Filter by provider, status, service, and appointment type.

## PriorityBook

The old project archive included a feature concept called PriorityBook. The purpose is to help clinics prioritize appointment requests and follow-ups.

MVP PriorityBook should be simple and explainable:

Priority score inputs:

- Service value: surgery, implants, high-ticket cosmetic procedures, advanced med spa packages.
- Lead intent: asked for price only vs asked to book vs deposit-ready.
- Urgency: wants appointment soon, pain/urgent dental issue, event/wedding deadline.
- Source quality: referral, chatbot qualified, email inquiry, paid ad, manual staff entry.
- Existing patient vs new patient.
- Follow-up status: uncontacted high-value requests should surface higher.

MVP output:

- Numeric score.
- Label: Low, Normal, High, Urgent/VIP.
- Reason text, such as `High-ticket service + requested this week`.

Do not make AI scoring a blocker for Step 2B. Start with rule-based scoring that can later be replaced or enhanced by AI.

## External Calendar Strategy

### Built-In Calendar First

The first version should work without Google Calendar, Calendly, or paid APIs. Clinics can manage requests and appointments inside ClinicPilot X immediately.

### Google Calendar Later

Google Calendar is a strong first external sync target because:

- It is widely used.
- Google Calendar API can check availability and create events.
- Google Meet links can be created through Calendar event conference data.

Compliance note:

- Google Workspace can support HIPAA use only when the clinic is on an eligible plan, signs Google's BAA, and configures services correctly.
- Avoid placing unnecessary PHI in event titles/descriptions. Use generic titles like `Clinic appointment` and store sensitive detail inside ClinicPilot X.

### Calendly Later

Calendly can be useful for general scheduling, but should not be the core healthcare booking source until compliance and PHI limits are reviewed.

Calendly API/webhooks can receive scheduled/cancelled/routing events, but Calendly webhooks and scheduling API features require paid Calendly plans. Calendly is also not designed to collect PHI.

MVP approach:

- Allow a clinic to store a Calendly link manually.
- Later, support Calendly webhooks for non-PHI booking metadata if the clinic chooses that workflow.

### Practice Management Systems Later

Dental and medical clinics may use platforms such as Dentrix, Eaglesoft, Open Dental, NexHealth, LocalMed, Solutionreach, Weave, PatientNow, Nextech, AestheticRecord, Boulevard, or ModMed.

Do not attempt broad PMS integration in the MVP. Instead:

- Design the appointment model with external IDs and source fields.
- Keep the integration architecture open.
- Start with Google Calendar/Calendly-style surfaces before specialized PMS integrations.

## Virtual Appointment Strategy

MVP:

- Let staff manually paste a Google Meet, Zoom, or telehealth link.
- Store it on the appointment.
- Show it clearly in appointment details.

Later:

- Generate Google Meet links via Google Calendar API when Google Calendar is connected.
- Support Zoom or other telehealth providers if a client requires it.
- Keep virtual meeting links out of public views unless the appointment is confirmed.

## Step 2B Recommended Scope

Build now:

- Replace calendar/appointment demo data with real Supabase data.
- Add appointment/request CRUD.
- Link appointments to leads/patients where possible.
- Add appointment statuses and filters.
- Add internal PriorityBook scoring fields.
- Add appointment detail drawer/modal.
- Add calendar item click behavior.
- Add safe drag/reschedule only if the chosen calendar component supports it cleanly.
- Keep Google Calendar, Calendly, Stripe, Twilio, VAPI, and n8n inactive for now.

Defer:

- Full Google Calendar OAuth.
- Calendly webhooks.
- Payment/deposit enforcement.
- Automated reminders.
- Chatbot booking automation.
- PMS integrations.

## Step 2B Acceptance Criteria

- Calendar and Appointments no longer show fake demo rows as if they are real.
- Staff can create an appointment request manually.
- Staff can link an appointment request to an existing lead if available.
- Appointment appears on both Appointments and Calendar.
- Changing date/time/status persists after refresh.
- Calendar click opens appointment details.
- Drag/reschedule works safely or is explicitly deferred.
- Priority label/score appears consistently.
- No external integrations are marked connected unless credentials/config are verified.

