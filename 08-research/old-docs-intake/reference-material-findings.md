# Reference Material Findings

Updated: 2026-05-22

Source folder:

`D:\PROJECTS\CLINICPILOT X (Old)`

These files are useful reference material, but they are not final product truth. Current product decisions should be captured in `PRODUCT_SPEC.md`, `DECISIONS.md`, `TASKS.md`, and current docs.

## Files Reviewed

The old archive contains:

- 28 Word documents.
- 9 n8n JSON workflow exports.
- 6 PDFs.
- 4 Excel workbooks.
- 4 PNG assets.
- 1 CSV checklist.

Generated inventory files:

- `08-research/old-docs-intake/old-project-intake-summary.md`
- `09-exports/old-project-inventory/old-project-file-inventory.csv`
- `04-automations/old-n8n-workflows/workflow-inventory.md`

## Key Product Concepts Found

- ClinicPilot as an AI-powered front desk assistant.
- Multi-channel intake: email, chatbot/Voiceflow, VAPI voice, SMS/Twilio, and form leads.
- Lead triage into leads, questionable/unsure, and spam.
- Google Sheets as an early unified lead database.
- Google Calendar smart booking and availability checks.
- Appointment hold system with expiration.
- Stripe/PayPal deposit links.
- Patient and staff notifications by email/SMS.
- Reminder cadence: 2 days, 1 day, and 2 hours before appointment.
- Outbound follow-up for stale leads.
- Daily briefing to clinic staff.
- Review/reputation requests after consult or procedure.
- PriorityBook lead/service scoring for revenue/urgency-based prioritization.
- Automation Center settings for clinic-specific rules.

## Existing n8n Workflow Exports

Copied into:

`04-automations/old-n8n-workflows`

Active in old exports:

- `[VAPI] inbound calling scenario.json`
- `Email Agent.json`
- `SMS messages.json`

Inactive/reference:

- `Daily data sending to clinic member.json`
- `NOTIFICATION.json`
- `outbound calling Voice workflow.json`
- `outbound reachout.json`
- `services credentials.json`
- `My workflow.json`

## Week-One Interpretation

The old docs describe a full automation platform. For the one-week MVP, do not try to rebuild everything. Focus on a narrow, demo-ready workflow:

1. Capture one inbound lead source.
2. Classify the inquiry.
3. Save the lead.
4. Notify the business owner.
5. Show the lead in the dashboard.
6. Generate a draft reply for human review.

Booking, payments, VAPI, SMS, reminders, reviews, and PriorityBook are valuable, but they should be staged after the base lead pipeline works.
