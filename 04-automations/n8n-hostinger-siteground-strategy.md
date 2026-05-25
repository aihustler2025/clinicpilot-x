# n8n, Hostinger, and SiteGround Strategy

Updated: 2026-05-25

## Current Known Context

The owner previously had n8n installed on Hostinger, but that hosting may be expired or inaccessible. The owner also has SiteGround hosting and wants to avoid unnecessary new monthly costs.

Existing n8n workflow exports were found in the old ClinicPilot X archive and copied into:

- `04-automations/old-n8n-workflows`

These include:

- Email Agent
- SMS Messages
- VAPI inbound calling scenario
- Daily data sending to clinic member
- Notification workflow
- Outbound calling workflow
- Outbound reachout workflow

## What Is Currently Powering Dashboard Lovable

Dashboard Lovable is currently powered by:

- Lovable frontend/app preview
- External Supabase project `zglkebeaimtvpynmlrra`
- Supabase Auth and role tables

n8n is not yet verified as connected to the live Dashboard Lovable app.

## Important Hosting Reality

n8n officially recommends Docker for most self-hosting. Self-hosting requires technical setup, server/security maintenance, persistent storage, backups, and uptime monitoring.

Shared hosting platforms usually are not ideal for n8n unless they support long-running Node.js apps, Docker, reverse proxy, HTTPS, background workers, and persistent storage. A VPS is normally the cleaner path.

SiteGround may be useful for ordinary websites, but should not be assumed to be suitable for production n8n until its plan capabilities are checked.

## Recommended MVP Strategy

For the next 7 days, prioritize speed and control:

1. Keep Dashboard Lovable + Supabase as the app/database.
2. Use imported n8n workflows as reference, not trusted production workflows.
3. Rebuild the first automation path cleanly:
   - inbound test email
   - classify email
   - save lead to Supabase
   - notify owner by email
   - draft reply, but do not auto-send yet
4. Avoid SMS/Twilio and VAPI until the email path works.
5. Do not move n8n to SiteGround unless SiteGround plan supports the required always-on runtime.

## Best Low-Cost Hosting Options

### Option A: Local n8n for build/testing

Cost:

- $0 beyond local machine.

Pros:

- Fastest for prototype.
- Good for importing old workflows and testing logic.

Cons:

- Not reliable for live client usage unless the machine stays online.
- Webhooks require tunneling or public endpoint setup.

### Option B: Small VPS for n8n

Cost:

- Usually low monthly cost, depending on provider.

Pros:

- Best balance for always-on workflows.
- Supports Docker, HTTPS, persistent volumes, and backups.
- Easier to control than shared hosting.

Cons:

- Requires server maintenance.

### Option C: SiteGround if plan supports it

Cost:

- Potentially $0 extra if already paid.

Pros:

- Reuses an account the owner already has.

Cons:

- Must verify Node.js/Docker/long-running process support.
- Shared hosting may not be appropriate for n8n.

### Option D: Make.com for proof of concept

Cost:

- Can start free/cheap depending on usage.

Pros:

- Fast setup, no server maintenance.

Cons:

- Less control.
- Can get expensive with higher usage.
- Harder to package as owned product infrastructure.

## Recommendation

Use local n8n or a temporary low-cost VPS for MVP automation testing. Do not rely on SiteGround until its capabilities are confirmed.

For a real pilot client:

- If workflows must run 24/7, use a VPS or n8n Cloud.
- If budget is the main constraint, use a small VPS and Docker.
- If speed matters more than infrastructure control, use Make.com temporarily and migrate later.

## Next Investigation Tasks

1. Check whether the old Hostinger account is still accessible.
2. If accessible, export:
   - workflows
   - credentials list, without exposing secrets in chat
   - environment settings
   - webhook URLs
   - n8n encryption key status
3. Check SiteGround plan capabilities:
   - Node.js app support
   - Docker support
   - SSH access
   - long-running process support
   - reverse proxy/custom port support
   - cron/background worker support
4. Decide n8n hosting path before connecting a live client.

## MVP Automation Scope

First automation to build:

- Gmail or inbox trigger for a controlled test email inbox.
- Classifier labels:
  - `credible_lead`
  - `spam`
  - `unsure`
  - `existing_client`
  - `vendor_or_solicitation`
- Extract:
  - name
  - email
  - phone
  - requested service
  - price/service question
  - urgency/timeframe
  - source
- Save to Supabase `leads`.
- Notify business owner by email.
- Draft reply for human approval.

