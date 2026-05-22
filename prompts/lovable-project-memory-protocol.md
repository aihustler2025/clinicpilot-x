# Lovable Project Memory Protocol

Use this instruction in Lovable for ClinicPilot X and future Buzzooka/Lovable projects.

```text
Before implementing new work, please follow this project memory protocol so the project does not drift or hallucinate over time.

Create and maintain an in-project documentation/status system that mirrors how Codex manages project memory. This should live inside the Lovable project/repo if GitHub sync is enabled, or as project docs/notes if a repo is not yet connected.

Required memory files:

1. AGENTS.md
- Operating instructions for Lovable/Codex/developers.
- Current project guardrails.
- What must not be changed without explicit approval.

2. STATUS.md
- Current state of the project.
- What is complete.
- What is partially complete.
- What is missing.
- What is the next immediate step.
- Update this after every meaningful implementation step.

3. TASKS.md
- Checklist of pending, in-progress, and completed tasks.
- Group tasks by Now, MVP, Later, Blocked, and Done.
- Do not mark tasks complete just because code was generated. Mark complete only when the feature is implemented and the expected behavior is described.

4. DECISIONS.md
- Important product, architecture, backend, hosting, integration, auth, and domain decisions.
- Include the reason for each decision.
- Include date and current status.

5. CHANGELOG.md
- Short history of changes made.
- Include pages changed, database changes, integrations changed, and deployment/domain changes.

6. PRODUCT_SPEC.md
- Current product definition and MVP scope.
- Do not let old ideas override the current MVP unless explicitly approved.

Working rules:

- Before making changes, summarize what you believe the current project state is.
- Before making changes, list the files/tables/features you plan to touch.
- After making changes, update STATUS.md, TASKS.md, DECISIONS.md if relevant, and CHANGELOG.md.
- If a user asks for a major feature, first classify it as MVP, later, or out-of-scope.
- If backend/domain/auth/integration changes are involved, ask for explicit approval before changing them.
- Do not invent connected integrations. If n8n, Supabase, Lovable Cloud, GitHub, Gmail, Twilio, VAPI, Stripe, PayPal, Voiceflow, or OpenAI is not actually connected, say so.
- Do not claim dashboard features are real if they use mock/static data.
- AI-generated patient/client replies must remain draft-only unless a specific auto-send workflow is explicitly approved.
```
