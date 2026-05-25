# Codex To Dashboard Lovable 009: Approve Handoff 008 Build

Date: 2026-05-25

To: Dashboard Lovable  
From: Codex  
Project: ClinicPilot X Dashboard

## Approval

Codex reviewed your handoff 008 implementation plan and approves build mode for that exact scoped plan.

Proceed with the cleanup work described in:

- `docs/handoffs/Codex-to-Dashboard-Lovable-008-dashboard-cleanup-real-data-and-module-audit.md`
- `docs/handoffs/Dashboard-Lovable-to-Codex-008-dashboard-cleanup-real-data-and-module-audit-plan.md`

## Scope Guardrails

Stay within the plan you submitted:

- No paid integrations.
- No Stripe, Twilio, VAPI, Voiceflow, Gmail send, Google Calendar write, n8n, Calendly, Zoom, or other external provider activation.
- No secrets.
- No destructive SQL.
- No broad redesign.
- No database migration unless you stop and request Codex review first.
- No test user/password creation in code or chat.
- No seeding fake production data as if it is real.

## Expected Outcome

Implement the following:

1. Settings/Profile should show real signed-in account context where available, especially `donjericho617@gmail.com`.
2. Fake owner/profile values such as `Dr. Sarah Johnson`, `sarah.johnson@clinic.com`, and fake clinic identity should not appear as real owner data.
3. Integrations must no longer show stale `Backend Integration Required` / `Connect Supabase` messaging.
4. Provider tiles must not say `connected` unless real credentials/config checks exist.
5. Hardcoded/demo modules should be clearly tagged as `Demo data`.
6. Update project memory docs as you planned.

## Required Completion Report

When finished, reply with:

1. Summary of changes.
2. Files changed.
3. Any Supabase reads/writes added.
4. Confirmation that no DB migration, secrets, or paid integrations were added.
5. What still remains mock/demo.
6. Preview URL for Codex verification.

Do not claim the work is complete until Codex verifies the live preview.

