# Handoff Naming Standard

Updated: 2026-05-22

This convention applies to ClinicPilot X and should be reused for future Buzzooka projects where Codex coordinates with Lovable or another AI/tool.

## Source Of Truth

Shared handoff files live here:

`docs/handoffs/`

Project operating docs live at repo root:

- `AGENTS.md`
- `STATUS.md`
- `TASKS.md`
- `DECISIONS.md`
- `CHANGELOG.md`
- `PRODUCT_SPEC.md`
- `README.md`
- `docs/NAMING.md`

## Filename Pattern

Outgoing from Codex:

`Codex-to-[Target]-Lovable-###-[short-topic].md`

Incoming from Lovable:

`[Target]-Lovable-to-Codex-###-[short-topic].md`

Where:

- `[Target]` is the Lovable project label, such as `Dashboard` or `Marketing`.
- `###` is a three-digit counter: `001`, `002`, `003`.
- `[short-topic]` is lowercase kebab-case.
- Extension is always `.md`.

## Counter Rules

- Codex creates and increments outgoing message numbers.
- Lovable should reply using the same number as the Codex message whenever possible.
- If Lovable sends multiple responses to one Codex message, suffix with a letter or more specific topic.

Examples:

- `Codex-to-Dashboard-Lovable-004-admin-access-recovery.md`
- `Dashboard-Lovable-to-Codex-004-admin-access-response.md`
- `Dashboard-Lovable-to-Codex-004b-admin-sql-followup.md`

## Examples

Codex to Dashboard Lovable:

- `Codex-to-Dashboard-Lovable-004-admin-access-recovery.md`
- `Codex-to-Dashboard-Lovable-005-handoff-naming-protocol.md`
- `Codex-to-Dashboard-Lovable-006-step-two-lead-intake-plan.md`

Dashboard Lovable to Codex:

- `Dashboard-Lovable-to-Codex-004-admin-access-response.md`
- `Dashboard-Lovable-to-Codex-005-handoff-naming-protocol-response.md`
- `Dashboard-Lovable-to-Codex-006-step-two-lead-intake-response.md`

Codex to Marketing Lovable:

- `Codex-to-Marketing-Lovable-001-audit-hold.md`
- `Codex-to-Marketing-Lovable-002-copy-checklist.md`
- `Codex-to-Marketing-Lovable-003-marketing-polish-plan.md`

Marketing Lovable to Codex:

- `Marketing-Lovable-to-Codex-001-audit-response.md`
- `Marketing-Lovable-to-Codex-002-copy-checklist-response.md`
- `Marketing-Lovable-to-Codex-003-marketing-polish-response.md`

## Response Header

Lovable should include this near the top of each response:

`Suggested response filename: Dashboard-Lovable-to-Codex-###-[short-topic].md`

or:

`Suggested response filename: Marketing-Lovable-to-Codex-###-[short-topic].md`

## Session Startup Rule

At the start of every new ClinicPilot X session, read:

1. `AGENTS.md`
2. `STATUS.md`
3. `TASKS.md`
4. `DECISIONS.md`
5. `docs/NAMING.md`

Then continue from the current task state.
