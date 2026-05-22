# ClinicPilot X Codex Operating Instructions

This folder is the persistent project memory for ClinicPilot X, a Buzzooka-owned product for lead intake, email triage, and automation workflows for clinics, med spas, dentists, salons, and similar service businesses.

## Source Of Truth

- GitHub/local project files are the project brain: instructions, tasks, product specs, decisions, status, changelog, prompts, and code exports.
- Google Drive is for heavy files: screenshots, videos, image assets, exports, client files, recordings, and large backups.
- The active local workspace is `D:\BUZZOOKA WORKSPACE\Products\ClinicPilot X`.
- Office PC and travel laptop are controllers/workstations. The external D drive is the portable active workspace.
- Lovable may currently hold the active marketing site, dashboard, backend, and generated app state. Until source code is exported, Lovable is an active build surface, not the full source of truth.
- Do not store passwords, API keys, GoDaddy credentials, SiteGround credentials, Supabase credentials, Lovable credentials, n8n secrets, Make credentials, or private client data in this repo.

## Start Every Session Here

1. Read `AGENTS.md`.
2. Read `STATUS.md`.
3. Read `TASKS.md`.
4. Read `PRODUCT_SPEC.md` if product direction is needed.
5. Read `DECISIONS.md` before changing hosting, backend, domain, database, automation, or compliance direction.

## Working Style

- Keep the project moving through documented tasks, not scattered chat memory.
- After meaningful work, update `STATUS.md`, `TASKS.md`, and `CHANGELOG.md`.
- Update `DECISIONS.md` when a product, architecture, vendor, hosting, backend, domain, or automation choice is made.
- For Lovable coordination, write clear copy-paste prompts in `prompts/` and verify actual behavior before marking tasks complete.
- For files shared by the owner, save or summarize them into the correct folder before relying on them.

## Product Guardrails

- MVP AI replies are draft-only unless the owner explicitly approves auto-send for a specific workflow.
- Treat medical, dental, beauty, and wellness inquiries carefully because messages may include sensitive personal or health information.
- Do not route sensitive health details into third-party tools unless compliance and data handling are understood.
- Start with email notifications before SMS because SMS has usage cost and deliverability requirements.
- Prefer a simple, sellable MVP over a broad unfinished platform.

## Current Build Surfaces

- Lovable: likely current frontend/dashboard/backend surface. Needs audit.
- GoDaddy: domain registrar. Needs DNS review before changes.
- SiteGround: existing hosting account. Needs cleanup/review before using for n8n or web hosting.
- Hostinger: may contain old self-hosted n8n. Status unknown.
- Make.com/n8n: candidate automation layer for MVP lead workflows.
- Cloudflare/Convex: available owner tools from other projects; candidate long-term product infrastructure.

## Current Delivery Pressure

The owner wants a usable client-ready MVP within roughly one week. Prioritize the shortest route to a reliable lead intake workflow over broad platform expansion.
