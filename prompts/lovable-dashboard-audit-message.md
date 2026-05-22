# Dashboard Lovable Audit Message

Send this to the Dashboard Lovable project.

```text
We are auditing the Dashboard Lovable project for ClinicPilot X. Please do not implement changes yet. This is a read-only audit and handoff request.

Important context:

- ClinicPilot X has at least two Lovable projects.
- The other project is now labeled Marketing Lovable and appears to contain only the public marketing website.
- This project is believed to contain the dashboard/admin/backend work.
- Codex is managing the project memory and will decide whether to merge the marketing website into this project or keep both projects separate.
- Desired domain is `clinicpilotx.com`, but DNS should not be changed yet.
- Existing GitHub repo prepared by Codex: `https://github.com/aihustler2025/clinicpilot-x`

Please provide a structured audit:

1. Project Identity
- Current project name.
- Lovable project ID.
- Current published/preview URLs.
- Whether this project is published.

2. Pages And Routes
- List every route/page.
- Mark each as dashboard/admin/user/auth/settings/public/other.
- Mark each as complete, partial, mock/static, broken, or unknown.

3. Dashboard Features
- List user dashboard modules.
- List admin dashboard modules.
- For each module, state whether it uses real data, mock data, hardcoded data, or no data.
- Identify the main user flows currently supported.

4. Backend And Database
- What backend is used: Lovable Cloud, standalone Supabase, external Supabase, no backend, or other?
- If Supabase is used, is it Lovable-managed or external?
- List all tables/entities and fields.
- List storage buckets, edge functions, server functions, webhooks, and RLS/security policies.

5. Auth And Roles
- Is authentication active?
- What provider/system is used?
- What roles exist?
- What pages are protected?
- Are admin/client/staff roles implemented?

6. Automations And Integrations
- Is n8n connected?
- If yes, list webhook names/purposes/triggers/payload shapes without exposing secret tokens.
- Are Gmail, Google Sheets, Google Calendar, Twilio, VAPI, Stripe, PayPal, Voiceflow, OpenAI, or Lovable AI Gateway connected?
- List environment variable names only, not secret values.

7. GitHub And Export
- Is GitHub sync enabled?
- What repo is connected?
- Can this project connect to `https://github.com/aihustler2025/clinicpilot-x`, or does Lovable require creating a new repo?

8. Merge Strategy
- Based on this project’s current state, should we:
  A. Make this Dashboard Lovable project the main app and copy/rebuild marketing pages into it?
  B. Keep Marketing Lovable separate on `clinicpilotx.com` and this project on `app.clinicpilotx.com`?
  C. Move dashboard/backend work into the Marketing Lovable project?
- Recommend the fastest and safest path to a client-ready MVP within one week.

9. Immediate Risks
- List anything that is broken, fake/mock, disconnected, or likely to block launch.

Do not implement anything yet. Return the audit only.
```
