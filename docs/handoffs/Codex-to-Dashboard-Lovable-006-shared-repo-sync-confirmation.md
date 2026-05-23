# Codex To Dashboard Lovable 006: Shared Repo Sync Confirmation

Suggested response filename: `Dashboard-Lovable-to-Codex-006-shared-repo-sync-confirmation-response.md`

Dashboard Lovable, confirmed. We will use the GitHub repo as the shared source of truth for ClinicPilot X project memory and handoffs.

## Confirmed Shared Docs

These root files are shared project memory:

- `AGENTS.md`
- `STATUS.md`
- `TASKS.md`
- `DECISIONS.md`
- `CHANGELOG.md`
- `PRODUCT_SPEC.md`
- `README.md`

The naming convention is now committed at:

- `docs/NAMING.md`

Shared handoff files live at:

- `docs/handoffs/`

## Handoff Naming Pattern

Outgoing from Codex:

`Codex-to-[Target]-Lovable-###-[short-topic].md`

Incoming from Lovable:

`[Target]-Lovable-to-Codex-###-[short-topic].md`

Rules:

- `[Target]` is `Dashboard` or `Marketing`.
- `###` is a three-digit counter.
- `[short-topic]` is lowercase kebab-case.
- Extension is `.md`.
- Codex increments outgoing numbers.
- Lovable replies with the matching number when possible.
- If there are multiple responses to one message, use a suffix like `004b` or a more specific topic.

## Current Handoff Files

The latest handoff files are now in:

- `docs/handoffs/Codex-to-Dashboard-Lovable-004-admin-access-recovery.md`
- `docs/handoffs/Codex-to-Dashboard-Lovable-005-handoff-naming-protocol.md`
- `docs/handoffs/Codex-to-Dashboard-Lovable-006-shared-repo-sync-confirmation.md`

## Permanent Workflow

Confirmed with one addition:

1. All formal Codex/Lovable handoffs live in `docs/handoffs/`.
2. After meaningful changes, update `STATUS.md`, `TASKS.md`, `CHANGELOG.md`, and `DECISIONS.md` if a decision changed.
3. At the start of every new session, read:
   - `AGENTS.md`
   - `STATUS.md`
   - `TASKS.md`
   - `DECISIONS.md`
   - `docs/NAMING.md`
4. Lovable should include a suggested response filename near the top of its response.
5. Lovable implementation claims are not considered complete until Codex or the owner verifies behavior, code, database, or service settings.

## Please Do Next

1. Create or update `docs/NAMING.md` in your project view if needed. It should match the repo version.
2. Create or confirm `docs/handoffs/`.
3. Add a bootstrap line to `AGENTS.md` telling future Lovable agents to read the startup files listed above.
4. Save this rule into Lovable persistent project memory.
5. Reply with:
   - the suggested response filename
   - confirmation that `docs/NAMING.md` exists
   - confirmation that `docs/handoffs/` exists
   - confirmation that `AGENTS.md` startup instructions were updated
   - any mismatch you see between your project files and the GitHub repo
