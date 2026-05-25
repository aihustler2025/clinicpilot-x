# Messaging Channel API Strategy

Updated: 2026-05-25

## Purpose

Decide how ClinicPilot X should eventually handle WhatsApp, Messenger, Instagram, and other messaging channels without creating unnecessary cost or compliance risk.

## Principle

For a sellable product used by real clinic clients, use official APIs or approved platform integrations.

Avoid unofficial WhatsApp Web/Desktop automation, scraping, browser-control bots, or reverse-engineered libraries for client-facing production use. They may appear cheaper, but they can break, violate platform terms, or risk account/number bans.

## Recommended Build Order

### MVP / Low Cost

Build source-aware Leads first:

- manual entry
- website contact form
- chatbot webhook
- email intake

This creates the same data path WhatsApp/Messenger can use later without paying for those channels immediately.

### Later: Official Meta Channels

Add:

- Messenger Platform for Facebook Page messages
- Instagram Messaging API for Instagram DMs
- WhatsApp Business Platform / Cloud API for WhatsApp

These should feed the same `leads` table and later a `messages` or `conversations` table.

### Optional Aggregator

Respond.io can act as an omnichannel inbox/automation layer, but it should remain optional.

As observed 2026-05-25, respond.io pricing starts at `$79/month`, with higher tiers at `$159/month` and `$279/month`. WhatsApp fees are not included in respond.io subscription pricing.

## WhatsApp

Cheapest legitimate long-term path:

- Use Meta WhatsApp Cloud API directly where possible.
- Avoid paying for a full inbox platform until a client needs it.

Expected costs:

- Meta usage fees for WhatsApp messages.
- Possible phone/business verification/onboarding work.
- Optional BSP/platform fees if using a provider.

Do not use:

- WhatsApp Web automation
- desktop app automation
- unofficial session APIs
- browser bots that imitate a human user

Reason:

- They may violate terms or break unpredictably.
- They are not a stable foundation for a clinic product.

## Messenger

Messenger can be integrated through Meta's Messenger Platform/Page messaging APIs.

Expected costs:

- No respond.io subscription required if built directly.
- Meta app setup, page connection, webhook verification, and policy compliance are required.
- Messaging windows and policy restrictions still apply.

## MCP / CLI / Local Automation

MCP or CLI tooling can help Codex/admin workflows and internal testing, but it should not be used to bypass platform APIs for production clinic messaging.

Acceptable uses:

- internal admin tools
- local testing
- importing/exporting data
- development automation

Not acceptable as product foundation:

- pretending to be a WhatsApp/Messenger user through a local app/browser to avoid official APIs
- client-facing message sending that depends on one computer staying online

## Product Architecture Recommendation

In Step 2A, only build Leads fields and UI that can receive channel metadata.

Later, add:

- `conversations` table
- `messages` table
- `channel_accounts` table
- webhook receiver/edge functions for each channel
- provider-specific integration settings

This prevents early vendor lock-in and keeps cost low.

