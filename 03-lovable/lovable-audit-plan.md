# Lovable Audit Plan

Updated: 2026-05-22

## Goal

Audit the current ClinicPilot X Lovable project before making changes to domain, backend, automations, or dashboard behavior.

Lovable project:

`https://lovable.dev/projects/37666967-bc8e-4032-9043-f45713e2bc22`

## Round 1

Use:

`prompts/lovable-audit-round-1-current-state.md`

Purpose:

- Get all routes/pages.
- Identify real vs mock dashboard data.
- Identify backend provider.
- Identify n8n/webhook/current automation connections.
- Identify GitHub sync/export status.
- Identify domain setup requirements for `clinicpilotx.com`.

## Round 2

After Lovable answers, Codex should:

1. Save Lovable's response into `03-lovable`.
2. Extract backend facts into `05-backend-data`.
3. Extract automation facts into `04-automations`.
4. Update `TASKS.md` with concrete implementation tasks.
5. Update `STATUS.md` with current project state.
6. Create the next Lovable implementation prompt only after the audit is reviewed.

## Do Not Do Yet

- Do not change DNS.
- Do not migrate backend.
- Do not connect new automations.
- Do not mark Lovable tasks complete from chat claims alone.
- Do not auto-send AI patient/client messages without an explicit approved workflow.
