# ClinicPilot X Status

Updated: 2026-05-22

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

Audit the separate `Dashboard Lovable` project before approving any backend/dashboard implementation in `Marketing Lovable`. Send `prompts/lovable-marketing-hold-message.md` to Marketing Lovable and `prompts/lovable-dashboard-audit-message.md` to Dashboard Lovable.

## Immediate Prompt To Use

Paste `prompts/lovable-audit-round-1-current-state.md` into the ClinicPilot X Lovable chat. Save Lovable's response into `03-lovable` before creating implementation prompts.

## Workspace Organization Update

On 2026-05-21, local storage was inspected. FanFlow's active repo is currently on the C drive at `C:\Users\Rosstafari\Documents\New project\FanFlow\cloud`, not on the D drive. D drive contains `BuzzForge`, `CLINICPILOT X (Old)`, `DASHCARDS`, `PRIME10X`, and `prime10x-homebase`. See `00-admin/workspace-inventory.md`.

On 2026-05-22, the active ClinicPilot X D-drive folder was created at `D:\BUZZOOKA WORKSPACE\Products\ClinicPilot X`.
