# Dashboard Priority Review

Updated: 2026-05-25

## Purpose

The Dashboard should give a clinic owner or manager a quick operational snapshot and the fastest path to the next important action.

## Current Dashboard Elements

Observed in the live preview:

- Today's Appointments
- New Leads
- Payments Collected
- Pending Follow-ups
- Quick Actions:
  - New Appointment
  - Start AI Call
  - Send SMS
  - Payment Link
- Recent Updates:
  - Alerts
  - Activity
- Today's Schedule

The page currently has a `Demo data` badge, so the content is not yet live.

## What Belongs On The MVP Dashboard

For the first clinic/client pilot, prioritize:

1. New leads needing attention.
2. Appointments today and upcoming.
3. Follow-ups due today.
4. Unsure/unclassified messages needing human review.
5. Automation health:
   - email intake connected or not
   - last email processed
   - last notification sent
6. Recent lead activity.

## Quick Actions Review

Keep only actions that actually work or can be wired soon.

Recommended MVP quick actions:

- Add Lead
- New Appointment
- Send Test Notification
- Open Review Queue

Hold or label as disabled until connected:

- Start AI Call
- Send SMS
- Payment Link

Reason:

- AI calls, SMS, and payment links involve paid providers and compliance/cost concerns.
- They should not look production-ready until VAPI/Twilio/Stripe are intentionally connected.

## Dashboard Questions For Owner

Ask/confirm:

1. Should the primary daily workflow be lead-first or appointment-first?
2. Do clients care more about missed leads, bookings, or revenue at first glance?
3. Should the dashboard be different for admin versus staff?
4. Should automation health be a top card?
5. Should quick actions be clinic operations actions or automation testing actions during MVP?

## Proposed MVP Dashboard Layout

Top cards:

- New Leads Today
- Leads Needing Review
- Appointments Today
- Follow-ups Due

Middle:

- Review Queue
- Today's Schedule

Bottom:

- Automation Health
- Recent Activity

Quick actions:

- Add Lead
- New Appointment
- Send Test Email Notification
- View Automation Logs

