# Lead Email Workflow

## Target Workflow

Inbound email arrives for a client business.

1. Capture email.
2. Classify message.
3. Extract structured lead data.
4. Save lead to CLINICPILOTX backend.
5. Notify business owner.
6. Draft a reply or place in review queue.

## Classification Labels

- `credible_lead`
- `spam`
- `unsure`
- `existing_client`
- `vendor_or_solicitation`

## Cheapest Test Options

- Make.com Free for fast visual proof of concept.
- Local n8n for experimentation.
- Cheap VPS/self-hosted n8n for always-on workflows.
- Cloudflare Worker plus Convex for product-owned infrastructure.

## MVP Recommendation

Start with email notifications only. Add SMS after the first paying client because SMS delivery has unavoidable usage costs.
