# ClinicPilot X Changelog

## 2026-05-26

- Adopted owner-approved assistant QA naming pattern: `CLINICPILOT QA {number}_{Module or Flow Name}`.
- Added `09-exports/README.md` so future assistant QA packages stay numbered and easy to hand off.
- Added Dashboard Lovable handoff 016 to fix the Leads `Created` timestamp display bug before Step 2B.
- Added Dashboard Lovable handoff 017 for the password reset `Auth session missing!` blocker and exact access links.
- Saved Dashboard Lovable's password reset completion report; owner confirmed password reset now works.
- Added Dashboard Lovable handoff 018 for the Add/Edit Lead modal tab-switch persistence bug found during assistant QA.
- Saved Dashboard Lovable's handoff 018 completion report.
- Added Dashboard Lovable handoff 019 to confirm which preview/published URL contains the fix for VA testing.
- Saved Dashboard Lovable's handoff 019 response confirming the preview URL contains the fix and publishing is not required for QA.
- Added Dashboard Lovable handoff 020 after owner/VA confirmed the Add Lead modal still closes on tab switch after hard refresh and fresh login.
- Saved Dashboard Lovable's handoff 020 response; Lovable acknowledged handoff 018 was insufficient and patched remount-safe Add/Edit Lead dialog state.
- Added Appointments and Calendar Step 2B strategy with internal calendar, appointment requests, PriorityBook, and integration deferral plan.
- Added Dashboard Lovable handoff 021 requesting a Step 2B plan for Appointments and Calendar.

## 2026-05-25

- Recorded owner app account email `donjericho617@gmail.com`.
- Recorded that the account signs in but is redirected to `/unauthorized`, meaning admin role promotion is still required.
- Added Supabase and Lovable Cloud cost audit notes with admin promotion SQL.
- Added backend cost audit tasks for Supabase billing and Lovable Cloud usage.
- Promoted `donjericho617@gmail.com` to admin in Supabase project `zglkebeaimtvpynmlrra`.
- Verified the admin role exists alongside the staff role for the owner account.
- Checked Supabase billing: `Buzzooka` is on Pro Plan with recent invoices around `$33-$35/month`.
- Ran a quick RLS policy verification query; it returned no public/anon full-access or plain true policies.
- Added Dashboard Lovable login/role access notes.
- Added assistant dashboard QA checklist for module testing.
- Confirmed in-app browser is logged into Dashboard Lovable as the admin account.
- Added live admin dashboard inventory across Dashboard, Calendar, Appointments, Leads, Patients, Staff, Automation Center, Voice Assistant, Payments, Integrations, Settings, and profile menu.
- Added Dashboard Lovable handoff 008 for removing placeholder messaging, clarifying mock vs real data, and preparing safe test data.
- Added n8n/Hostinger/SiteGround automation hosting strategy.
- Added client pilot test data plan using Gmail plus-addressing.
- Saved and reviewed Dashboard Lovable's handoff 008 implementation plan.
- Added Dashboard Lovable handoff 009 to explicitly approve the scoped handoff 008 build.
- Saved Dashboard Lovable's handoff 008 completion report for Codex verification.
- Verified Dashboard Lovable handoff 008 in the live preview and recorded the results.
- Added Dashboard Lovable handoff 010 for the false `/unauthorized` redirect bug.
- Added assistant QA script for auth redirect and leads observation testing.
- Saved Dashboard Lovable auth redirect analysis and approved the narrow frontend fix.
- Added dashboard priority review for MVP dashboard content and quick actions.
- Saved Dashboard Lovable auth fix completion report and verified signed-in admin refresh/deep-link behavior.
- Added dashboard and Leads QA first-pass findings.
- Added Dashboard Lovable handoff 012 for dashboard quick-action cleanup and Leads Supabase CRUD planning.
- Captured multi-source Leads strategy covering manual, chatbot, contact form, email, Messenger, WhatsApp, Meta leads, and future aggregators.
- Added cost/API watchlist for paid dependencies.
- Added Dashboard Lovable handoff 013 as a source-aware Leads addendum before Step 2A planning.
- Saved Dashboard Lovable Step 2A Leads CRUD plan and approved it with additive migration guardrails.
- Added messaging channel/API strategy for WhatsApp, Messenger, respond.io, MCP/CLI, and future channel architecture.
- Saved Dashboard Lovable update that the Leads migration applied and build mode is pending.
- Added Dashboard Lovable handoff 015 to proceed with Step 2A build.
- Recorded owner confirmation to avoid unofficial WhatsApp/Messenger automation for production.
- Saved Dashboard Lovable Step 2A completion report.
- Verified Step 2A dashboard quick actions and Leads empty/review UI.
- Noted that full lead CRUD verification is pending manual form entry due to browser text-entry limitations.
- Verified full Leads create/search/edit/refresh persistence for a test lead.
- Logged a follow-up issue for the Leads Created timestamp showing `about 8 hours ago` immediately after creation.
- Added assistant-facing Leads module Step 2A QA script.

## 2026-05-22

- Created active D-drive project folder at `D:\BUZZOOKA WORKSPACE\Products\ClinicPilot X`.
- Copied existing ClinicPilot X project memory docs from the C-drive workspace.
- Updated project docs with official name, active location, one-week MVP urgency, and backend audit questions.
- Initialized local Git repo and added a starter `.gitignore`.
- Renamed local Git branch to `main`.
- Added Lovable backend/cloud audit prompt.
- Added one-week MVP launch plan.
- Added GitHub repo creation instructions.
- Added hosting cleanup and n8n SiteGround prompt.
- Added Lovable project manager master audit prompt.
- Created private GitHub repo `aihustler2025/clinicpilot-x`.
- Connected local D-drive repo to GitHub and pushed initial project memory commit.
- Inventoried old ClinicPilot X archive at `D:\PROJECTS\CLINICPILOT X (Old)`.
- Copied old n8n workflow exports into active project automation folder.
- Generated old document intake summary and file inventory.
- Added Lovable project inventory.
- Added domain plan for `clinicpilotx.com`.
- Added Lovable audit round 1 current-state prompt and audit plan.
- Extracted Lovable chat history attachment.
- Added Lovable audit round 1 findings.
- Added Lovable project memory protocol.
- Added custom response to send instead of broad approval.
- Reclassified audited Lovable project as `Marketing Lovable`.
- Added two-project strategy doc.
- Added Marketing Lovable hold message and Dashboard Lovable audit message.
- Extracted combined Marketing/Dashboard Lovable responses.
- Recommended Dashboard Lovable as the main app.
- Added merge recommendation and Step 1 security/auth prompt.
- Extracted second Marketing/Dashboard Lovable response.
- Reviewed Dashboard Lovable Step 1 security/auth plan.
- Added Step 1 approval prompt with guardrails.
- Added ClinicPilot X product ecosystem vision covering chatbot plugin, website package, and future staff app.
- Extracted Dashboard Lovable build-mode request.
- Added review recommending approval for Step 1 app code only.
- Extracted Dashboard Lovable Step 1 completion report.
- Added Step 1 completion review and admin access recovery prompt.
- Added Lovable QA protocol and verification rule.
- Added Lovable handoff naming system and numbered outgoing admin-access file.
- Added global Buzzooka AI-to-AI handoff naming standard.
- Added Dashboard Lovable handoff naming protocol message.
- Added repo-visible `docs/NAMING.md` and `docs/handoffs/` for Dashboard Lovable.
- Added shared repo sync confirmation handoff 006.
- Made GitHub repo public for Lovable read access.
- Added handoff 007 with full public repo context and admin access request.
- Saved Dashboard Lovable 007 admin access response.
- Added admin access verification plan.

## 2026-05-21

- Created CLINICPILOTX project memory files.
- Added operating instructions for Codex sessions.
- Added initial status, task list, product spec, and decisions log.
- Added Lovable, backend, domain, hosting, and automation intake tasks.
- Inspected C-drive and D-drive project locations.
- Added workspace inventory documenting FanFlow, BuzzForge, Prime10X, Dashcards, and CLINICPILOTX local storage state.
