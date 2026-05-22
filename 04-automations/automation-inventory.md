# Automation Inventory

Updated: 2026-05-22

## Current Known Automation Sources

Old n8n workflow exports were found in:

`D:\PROJECTS\CLINICPILOT X (Old)\Dawood`

They were copied into the active project folder:

`04-automations/old-n8n-workflows`

## Old Active Workflows

### Email Agent

Purpose inferred from nodes:

- Gmail trigger receives email.
- LangChain/Gemini calendar booking agent processes requests.
- Google Calendar availability/event tools are used.
- Gmail sends a response.
- Google Sheets logs inquiry and appointment data.

Risk:

- Credentials, trigger account, sheet IDs, and calendar IDs must be audited before reuse.

### SMS Messages

Purpose inferred from nodes:

- Twilio trigger receives SMS.
- LangChain/Gemini/OpenAI nodes process the conversation.
- Twilio sends SMS/WhatsApp/MMS response.
- Google Sheets logs inquiry and appointment data.
- Calendar tools support booking.

Risk:

- Twilio costs money and needs compliant opt-in/quiet-hour handling.

### VAPI Inbound Calling Scenario

Purpose inferred from nodes:

- Webhook receives VAPI voice-call payload.
- Agent checks calendar availability.
- Google Sheets logs inquiry and appointment data.
- Webhook response returns call outcome.

Risk:

- VAPI credentials, agent configuration, and webhook endpoint are unknown.

## MVP Recommendation

For the first client-ready version, rebuild or verify only the email intake path:

1. Inbound email/form lead.
2. Classify as credible lead, spam, unsure, existing client, vendor/solicitation.
3. Save lead.
4. Notify owner by email.
5. Draft reply but do not auto-send without approval.

After the email path works, add SMS/Twilio and VAPI as paid or advanced modules.
