# Codex To Dashboard Lovable 013: Lead Source Strategy Addendum

Date: 2026-05-25

To: Dashboard Lovable  
From: Codex  
Project: ClinicPilot X Dashboard

## Context

Before you respond to handoff 012, please also read this addendum.

Relevant docs:

- `docs/handoffs/Codex-to-Dashboard-Lovable-012-dashboard-priority-and-leads-crud-plan.md`
- `02-product/lead-source-strategy.md`
- `00-admin/cost-and-api-watchlist.md`

## Owner Lead Vision

The Leads module should support leads from multiple real-world sources:

- manual entry
- chatbot / website widget
- website contact form
- email inbox
- Facebook Messenger
- WhatsApp
- Facebook/Meta lead ads
- Instagram DMs later
- voice/call sources later
- third-party aggregators such as respond.io later

The owner wants a demo flow where a prospect interacts with a clinic website/chatbot, submits lead details, and that lead appears in ClinicPilot X.

## Important Product Direction

For Step 2A, do not integrate all channels yet. But design the Leads data model/UI so it does not paint us into a corner.

Leads should include source-aware fields where the existing table allows it, or you should propose the smallest DB migration if fields are missing:

- source
- source detail/channel
- service interest
- status
- notes
- original message/conversation summary where possible
- assigned staff
- follow-up due date
- last contacted timestamp
- contact consent/opt-in where needed later

## Recommended MVP Source Priority

Build now or plan now:

1. Manual entry
2. Website contact form
3. Chatbot/webhook source
4. Email intake source

Do not wire yet unless explicitly approved:

- WhatsApp
- Messenger
- Instagram DMs
- SMS/Twilio
- VAPI/voice
- Stripe/payments
- respond.io

## Cost Guardrail

The owner wants to keep monthly/API costs low.

Do not add respond.io, WhatsApp API, Twilio, VAPI, Stripe, or another paid dependency in Step 2A.

If you think one is required, stop and explain:

- vendor
- why needed
- monthly cost
- usage cost
- whether there is a cheaper/manual alternative

## Step 2A Plan Must Include

In your response to handoff 012, add:

1. How the Leads schema/UI will represent source channels.
2. Whether current `leads` table supports chatbot/contact-form/email/manual leads.
3. Whether a small migration is needed for source/channel/message/assignment/follow-up metadata.
4. How manual Add Lead will work for test data.
5. How future chatbot/contact-form/email webhooks can create leads without rebuilding the whole page.
6. What will remain future work for Messenger/WhatsApp/respond.io.

Do not build yet. Reply with the updated plan first.

