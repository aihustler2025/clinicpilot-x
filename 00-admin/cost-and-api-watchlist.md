# Cost and API Watchlist

Updated: 2026-05-25

## Purpose

Track tools, APIs, subscriptions, and usage-based services before ClinicPilot X depends on them.

## Active / Known Costs

### Supabase

- Current status: active
- Organization: `Buzzooka`
- Plan observed: Pro
- Recent invoices observed: about `$33-$35/month`
- Use: Dashboard Lovable backend/auth/database
- Decision: keep for now because already active and working

### Lovable

- Current status: active
- Owner reported plan: about `$50/month`
- Use: Dashboard/marketing app builder and preview hosting
- Decision: continue for now while Dashboard Lovable remains the fastest path

### Chatbot Platform

- Current status: owner reports currently paying
- Vendor/spelling: needs confirmation; owner said something like `Convocore`
- Use: chatbot on client/demo website
- Decision: identify exact tool, cost, export/integration options, webhook support

## Candidate Future Costs

### respond.io

- Current pricing observed 2026-05-25:
  - Starter: `$79/month`
  - Growth: `$159/month`
  - Advanced: `$279/month`
- WhatsApp fees: not included; Meta charges separately
- Use: omnichannel inbox/lead aggregation
- MVP decision: do not require; optional later connector

### WhatsApp Business Platform

- Cost type: Meta usage fees, plus any BSP/platform fees
- Use: WhatsApp lead intake and replies
- MVP decision: support source field now; connect later when needed

### Twilio

- Cost type: phone/SMS/WhatsApp usage
- Use: SMS reminders and notifications
- MVP decision: defer until email path works or paying client needs SMS

### VAPI / Voice Provider

- Cost type: voice minutes, phone numbers, AI/model usage
- Use: voice assistant and calls
- MVP decision: defer until lead/email workflow is stable

### Stripe

- Cost type: payment processing fees
- Use: payments/payment links
- MVP decision: keep UI disabled/demo until explicitly planned

## Rule

Before adding a paid dependency, Codex should update this file and ask the owner to confirm the cost/risk.

