# Lead Source Strategy

Updated: 2026-05-25

## Owner Vision

ClinicPilot X should capture and manage leads from multiple sources, not only manual entry.

Important lead sources:

- Manual entry
- Chatbot / website widget
- Website contact form
- Email inbox
- Facebook Messenger
- WhatsApp
- Facebook/Meta lead ads
- Instagram DMs, later
- Phone/voice assistant, later
- Other aggregators/inboxes, later

The owner wants a demo website connected to a chatbot so a 15-minute sales presentation can show:

1. the clinic website,
2. the chatbot interaction,
3. captured lead details,
4. the lead appearing inside ClinicPilot X,
5. follow-up/notification workflows.

## Product Direction

Leads should be source-aware from the beginning.

Every lead should ideally include:

- name
- email
- phone
- source
- source detail/channel
- service interest
- lead status
- qualification/classification
- notes/conversation summary
- original message/transcript where available
- assigned staff member
- follow-up due date
- last contacted timestamp
- consent/opt-in flags when relevant

## Recommended MVP Source Priority

### Phase 1: Lowest Cost / Highest Control

1. Manual entry
2. Website contact form
3. Chatbot webhook
4. Email intake

Reason:

- These are controllable and cheap.
- They do not require paid WhatsApp/SMS/voice provider setup.
- They cover a strong client demo.

### Phase 2: Common Client Channels

1. Facebook Messenger
2. WhatsApp
3. Instagram DMs
4. Facebook/Meta lead ads

Reason:

- Clinics, spas, salons, and dental offices often receive leads from social channels.
- These channels may require Meta setup, webhooks, app review, business verification, or paid platform/API costs.

### Phase 3: Advanced / Paid

1. SMS/Twilio
2. VAPI or voice calls
3. Stripe/payment follow-ups
4. Omnichannel inbox tools such as respond.io

Reason:

- These can become expensive or operationally heavy.
- They should be added when a paying client justifies the cost.

## Respond.io Note

Respond.io is a possible omnichannel inbox/automation platform for WhatsApp, Messenger, Instagram, TikTok, email, webchat, and similar channels.

As of the 2026-05-25 pricing check, respond.io lists:

- Starter: `$79/month`
- Growth: `$159/month`
- Advanced: `$279/month`

WhatsApp fees are not included in the respond.io subscription; Meta charges WhatsApp usage separately.

Recommendation:

- Do not make respond.io a required MVP dependency.
- Keep it as an optional future connector/integration.
- Build ClinicPilot so it can ingest messages/leads by webhook/API later.

## Chatbot Note

The owner mentioned a current paid chatbot/tool subscription, possibly "Convocore" or a similarly named platform. The exact vendor/spelling still needs confirmation.

The chatbot should be treated as an external lead source for the first MVP:

- chatbot captures visitor name/contact/service question
- chatbot sends webhook payload to ClinicPilot or automation engine
- ClinicPilot creates/updates a lead
- dashboard shows the lead source as `chatbot`

Longer term, the owner wants to build a ClinicPilot chatbot/plugin product in-house or under the Buzzooka/ClinicPilot ecosystem. That should wait until the dashboard and automation engine are stable enough for a client pilot.

## Cost Guardrail

Do not add paid APIs or platform dependencies without recording:

- vendor
- purpose
- monthly base cost
- usage cost
- required credentials
- cancellation risk
- whether it is required for MVP or optional

