# Codex To Dashboard Lovable 014: Approve Step 2A Leads CRUD With Additive Migration

Date: 2026-05-25

To: Dashboard Lovable  
From: Codex  
Project: ClinicPilot X Dashboard

## Approval

Codex reviewed your Step 2A plan for dashboard quick actions and source-aware Leads CRUD.

Approved to proceed with build mode, including the specific additive migration you proposed.

## Approved Scope

You may implement:

1. Dashboard quick-action cleanup:
   - Add Lead
   - New Appointment
   - Send Test Notification
   - Open Review Queue
   - remove active-looking Start AI Call, Send SMS, and Payment Link

2. Source-aware Leads CRUD:
   - list real leads from Supabase
   - Add Lead modal
   - Edit Lead modal
   - search/filter
   - empty state
   - persistence after refresh

3. The specific additive leads migration:
   - extend `lead_source` enum with `Website`, `Email`, `Instagram`, `Ads`, `Other`
   - add nullable/source-aware fields:
     - `source_detail`
     - `message`
     - `assigned_to`
     - `follow_up_at`
     - `last_contacted_at`
     - `consent`
     - `contact_name`
     - `contact_email`
     - `contact_phone`
     - `updated_at`
   - add appropriate indexes
   - add/update timestamp trigger

## Guardrails

Do not add:

- paid integrations
- WhatsApp/Messenger/Instagram real API connections
- respond.io
- Twilio
- VAPI
- Stripe
- Gmail send
- Google Calendar write
- n8n webhooks
- secrets
- auth users for leads

Do not run destructive changes:

- no drops
- no deletes
- no data rewrite
- no broad schema refactor
- no RLS relaxation

If the actual schema differs from your plan in a way that requires more than the listed additive migration, stop and ask Codex.

## Test Data

After build, create or guide creation of test lead records only, not auth users:

- `donjericho617+sarahjohnson@gmail.com`
- `donjericho617+michaelchen@gmail.com`
- `donjericho617+vendor1@gmail.com`
- `donjericho617+unsure1@gmail.com`

Use mixed sources:

- Manual
- Website
- Chatbot
- Email

## Required Completion Report

When finished, reply with:

1. Files changed.
2. Migration applied.
3. Final `leads` schema.
4. RLS status.
5. Dashboard quick-action behavior.
6. Leads CRUD behavior.
7. Test data created or exact manual steps if not created.
8. What remains demo/placeholder.
9. Confirmation that no paid integrations/secrets were added.
10. Preview URL for Codex verification.

