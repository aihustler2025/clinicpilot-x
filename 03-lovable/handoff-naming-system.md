# Lovable Handoff Naming System

Updated: 2026-05-22

## Purpose

Use numbered Markdown files for messages between Codex and Lovable so the conversation stays easy to follow, archive, and resend.

## Folders

Outgoing messages from Codex to Lovable:

`03-lovable/handoffs/outgoing-to-lovable`

Incoming responses from Lovable to Codex:

`03-lovable/handoffs/incoming-from-lovable`

## Naming Format

Use this pattern:

`Codex-to-[Target]-Lovable-###-[short-topic].md`

`[Target]-Lovable-to-Codex-###-[short-topic].md`

Examples:

- `Codex-to-Marketing-Lovable-001-audit-hold.md`
- `Marketing-Lovable-to-Codex-001-audit-response.md`
- `Codex-to-Dashboard-Lovable-004-admin-access-recovery.md`
- `Dashboard-Lovable-to-Codex-004-admin-access-response.md`

## Current Next File

Send this file to Dashboard Lovable next:

`03-lovable/handoffs/outgoing-to-lovable/Codex-to-Dashboard-Lovable-004-admin-access-recovery.md`

## Workflow

1. Codex creates a numbered outgoing `.md` file.
2. Owner opens the outgoing handoff folder.
3. Owner uploads/drags the `.md` file into Lovable or opens it and copies the text.
4. Owner saves Lovable's response as a numbered incoming file or sends the exported response back to Codex.
5. Codex extracts the response, reviews it, updates project memory, and creates the next numbered outgoing file.

## Rule

The numbered handoff files are for human/tool communication. The `prompts/` folder can still keep reusable internal prompt templates.

## Other AI Response Instruction

When sending a numbered handoff to Lovable, ask Lovable to include a suggested response filename near the top of its answer:

`Suggested response filename: Dashboard-Lovable-to-Codex-###-[short-topic].md`

This lets the owner save Lovable responses without inventing filenames manually.
