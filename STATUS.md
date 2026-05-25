# ClinicPilot X Status

Updated: 2026-05-25

## Current Stage

Project setup and intake. The owner has an existing Lovable-built project with a marketing website and dashboard estimated around 50-70% complete. Codex has created the active D-drive ClinicPilot X project memory folder and is preparing to audit Lovable, domain, backend, and automation setup.

## Known Context

- ClinicPilot X is a Buzzooka-owned product.
- Active local folder: `D:\BUZZOOKA WORKSPACE\Products\ClinicPilot X`
- GitHub repo: `https://github.com/aihustler2025/clinicpilot-x`
- Lovable project: `https://lovable.dev/projects/37666967-bc8e-4032-9043-f45713e2bc22`
- Lovable project labels: `Marketing Lovable` for the audited static website project; `Dashboard Lovable` for the separate app/dashboard project still pending audit.
- Target domain: `clinicpilotx.com`
- The owner wants a usable MVP in about one week because clients are waiting.
- Target customers include plastic surgery clinics, dentists, dental surgery offices, med spas, beauty spas, hair salons, beauty parlors, and similar service businesses.
- Core MVP: classify inbound client emails, identify credible leads, notify the business owner, save lead records, and optionally draft replies.
- Lovable currently holds important build work. It should not be discarded until audited.
- Owner uses GitHub/local files as the project brain and Google Drive for heavy assets/backups.
- Owner works across office PC and travel laptop, so markdown continuity files are required.

## Unknowns To Verify

- Lovable project URL/ID.
- Whether Lovable project can export to GitHub.
- Whether Lovable backend is Supabase, Lovable Cloud, or something else.
- Whether dashboard is connected to real data or mock data.
- Domain name and current GoDaddy DNS records.
- Current SiteGround hosting contents and whether it should be cleaned up or reused.
- Whether Hostinger n8n still exists and can be exported.
- Whether Make.com or n8n is the first automation path.

## Intake From Old Project Files

On 2026-05-22, Codex inventoried `D:\PROJECTS\CLINICPILOT X (Old)`. The archive contains old docs, n8n workflow exports, PDFs, spreadsheets, and images. Key findings were saved in `08-research/old-docs-intake/reference-material-findings.md`, and old n8n exports were copied to `04-automations/old-n8n-workflows`.

## Marketing Lovable Audit Round 1 Findings

Lovable reports the audited project is a static marketing site only. There is no dashboard, no backend, no Lovable Cloud, no Supabase, no auth, no database, no n8n, and no active integrations. The contact form only shows a toast and discards lead data. This project is now labeled `Marketing Lovable`. See `03-lovable/lovable-audit-round-1-findings.md`.

## Next Best Step

Choose Dashboard Lovable as the likely main app, but require a security/auth implementation plan before approving changes. Send `prompts/lovable-dashboard-step-1-security-auth-plan.md` to Dashboard Lovable. Keep Marketing Lovable on hold with `prompts/lovable-marketing-pause-after-combined-audit.md`.

## Combined Lovable Audit Summary

Marketing Lovable is static marketing only. Dashboard Lovable has dashboard routes and an external Supabase project (`zglkebeaimtvpynmlrra`) with tables, but critical security/auth work is missing. The recommended path is to make Dashboard Lovable the main app and port Marketing Lovable pages into it after security/auth are fixed.

## Dashboard Step 1 Plan Review

Dashboard Lovable proposed a security/auth/roles plan. It is acceptable with guardrails: project memory should be real files where possible, no destructive data changes, no public lead capture in Step 1, and admin bootstrap must be explicit and safe. Use `prompts/lovable-dashboard-step-1-approve-with-guardrails.md`.

## Dashboard Step 1 Build Approval

Dashboard Lovable reports the Step 1 database migration has already been applied and is now asking to enter build mode for auth/protected routes/project memory files only. Approved path: click Approve if the scope shown is limited to Step 1 app code and memory files. See `03-lovable/dashboard-step-1-build-approval-review.md`.

## Dashboard Step 1 Completion

Dashboard Lovable reports Step 1 is complete: auth routes, protected routes, role filtering, project memory files, and role-scoped RLS policies are in place. Next step is to establish/verify owner admin access safely. Do not ask for or reveal passwords. Use `prompts/lovable-dashboard-admin-access-recovery.md`.

## QA Rule

Lovable implementation claims must be verified before being treated as complete. See `03-lovable/lovable-qa-protocol.md`. Dashboard Step 1 is reported complete by Lovable but still needs independent verification after admin access is established.

## Lovable Handoff System

Use numbered Markdown files for Codex/Lovable messages. Current next outgoing file: `03-lovable/handoffs/outgoing-to-lovable/Codex-to-Dashboard-Lovable-004-admin-access-recovery.md`. Naming rules are in `03-lovable/handoff-naming-system.md`.

## Global Handoff Standard

The same AI-to-AI handoff naming system should apply across Buzzooka projects and tools. Global standard saved at `D:\BUZZOOKA WORKSPACE\00-global-systems\handoff-protocols\ai-to-ai-handoff-naming-standard.md`.

## Shared Repo Sync With Dashboard Lovable

Dashboard Lovable requested a repo-visible naming convention and shared handoff path. Codex created `docs/NAMING.md`, `docs/handoffs/`, and `docs/handoffs/Codex-to-Dashboard-Lovable-006-shared-repo-sync-confirmation.md`.

## Repo Visibility

On 2026-05-23, Codex changed `https://github.com/aihustler2025/clinicpilot-x` from private to public so Lovable can read shared docs and handoffs directly from GitHub. Next handoff is `docs/handoffs/Codex-to-Dashboard-Lovable-007-public-repo-context-and-admin-access.md`.

## Admin Access Setup

Dashboard Lovable confirmed there are no existing Supabase Auth users and no admin role yet. Next step is to create the owner account at the Dashboard Lovable `/auth` preview, promote that email to admin in Supabase SQL editor, and verify protected routes/RLS before Step 2. See `03-lovable/admin-access-verification-plan.md`.

## Admin Account Update

The owner created and verified the app account `donjericho617@gmail.com`. On 2026-05-25, Codex promoted this account to `admin` in Supabase project `zglkebeaimtvpynmlrra`. Verification returned both `admin` and `staff` roles for the account. Next action: sign into the Dashboard Lovable preview with this email and verify admin routes.

Login clarification: there is one shared Dashboard Lovable login page at `/auth`. Admin and staff are roles on the same account system, not separate login portals. See `03-lovable/dashboard-login-and-role-access.md`.

## Backend Cost Audit

The owner wants to avoid duplicate backend costs. Current evidence still points to Dashboard Lovable using standalone Supabase, not Lovable Cloud. The relevant Supabase organization is `Bazooka`; the relevant project is likely `Prime Clinic Pilot`. Cost status depends on the actual Supabase plan and active project count. Notes and admin SQL are saved in `05-backend-data/supabase-lovable-cloud-cost-audit.md`.

Supabase dashboard now shows the `Buzzooka` organization is on the `Pro Plan`, spend cap is enabled, and recent invoices are around `$33-$35/month`. Active projects shown include `clinicpilot` and `Prime10XSocialFi`; `Video Muse` is paused. Lovable Cloud migration should not be treated as a simple switch because Lovable currently documents that migration from an existing Supabase project to Lovable Cloud is not supported.

## QA Preparation

Codex created an assistant QA checklist for Dashboard Lovable module testing at `09-exports/assistant-dashboard-qa-checklist.md`. Direct Codex browser QA still needs an authenticated dashboard session.

## Live Dashboard Admin Inventory

On 2026-05-25, Codex confirmed the in-app browser is logged into the Dashboard Lovable preview as `donjericho617@gmail.com` with the `admin` role. All major admin/sidebar routes loaded without redirecting to `/auth` or `/unauthorized`. First-pass inventory is saved at `03-lovable/dashboard-live-admin-inventory-2026-05-25.md`.

Priority findings: Settings shows demo account/clinic data, Integrations still displays a stale `Connect Supabase` / backend-required message, and many modules appear to contain demo/static data until create/update/persistence is tested.

Next Dashboard Lovable handoff: `docs/handoffs/Codex-to-Dashboard-Lovable-008-dashboard-cleanup-real-data-and-module-audit.md`.

Dashboard Lovable replied with an acceptable scoped plan for handoff 008. The plan is saved at `docs/handoffs/Dashboard-Lovable-to-Codex-008-dashboard-cleanup-real-data-and-module-audit-plan.md`. Build approval is acceptable if the blue Approve button corresponds exactly to this plan.

## Automation Hosting Strategy

Old n8n workflows exist in `04-automations/old-n8n-workflows`, but n8n is not yet verified as connected to the live Dashboard Lovable app. Hostinger may have held a prior n8n instance; SiteGround may be available but must be checked for Docker/Node/long-running process support before using it for n8n. Strategy notes are saved in `04-automations/n8n-hostinger-siteground-strategy.md`.

## Product Ecosystem Vision

The owner described a broader ClinicPilot X ecosystem: main dashboard, embeddable chatbot plugin, clinic website package, and future staff/in-house app. This is captured in `01-strategy/product-ecosystem-vision.md`, but it should not delay the immediate MVP/security work.

## Immediate Prompt To Use

Paste `prompts/lovable-audit-round-1-current-state.md` into the ClinicPilot X Lovable chat. Save Lovable's response into `03-lovable` before creating implementation prompts.

## Workspace Organization Update

On 2026-05-21, local storage was inspected. FanFlow's active repo is currently on the C drive at `C:\Users\Rosstafari\Documents\New project\FanFlow\cloud`, not on the D drive. D drive contains `BuzzForge`, `CLINICPILOT X (Old)`, `DASHCARDS`, `PRIME10X`, and `prime10x-homebase`. See `00-admin/workspace-inventory.md`.

On 2026-05-22, the active ClinicPilot X D-drive folder was created at `D:\BUZZOOKA WORKSPACE\Products\ClinicPilot X`.
