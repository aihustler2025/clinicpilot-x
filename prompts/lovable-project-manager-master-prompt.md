# Lovable Project Manager Master Prompt

Use this in Lovable for the main ClinicPilot X audit.

```text
We are preparing ClinicPilot X for a one-week MVP launch. Codex is acting as project manager and technical lead. Please do not make changes yet. First, provide a complete audit.

Project context:

ClinicPilot X is a Buzzooka-owned product for clinics, med spas, dental practices, beauty spas, salons, and other service businesses. The MVP should automate lead intake, classify inbound inquiries, save credible leads, notify the business owner, and draft replies for review.

Please audit the current Lovable project and answer in a structured handoff format:

1. What is the current app name and project ID?
2. What pages/routes exist?
3. Which routes are public marketing pages?
4. Which routes are authenticated dashboard/admin pages?
5. Which screens are complete enough for MVP?
6. Which screens are placeholder/mock/demo only?
7. What backend is currently used: Lovable Cloud, standalone Supabase, external Supabase, no backend, or something else?
8. If Supabase is used, is it managed by Lovable or connected externally?
9. What tables/entities currently exist?
10. What fields exist in each table/entity?
11. What auth provider and roles are configured?
12. What integrations are connected?
13. Is n8n currently connected? If yes, list every webhook URL, workflow purpose, trigger, and expected payload shape without revealing secrets.
14. Are there any email automations already configured?
15. Are there any notification automations already configured?
16. What environment variables are required? Do not reveal secret values.
17. Can this project sync/export to GitHub?
18. If a GitHub repo is connected, what repo is it?
19. Can the project be migrated to Lovable Cloud without data loss or feature breakage?
20. What would you recommend as the safest next steps to ship a client-ready MVP in one week?

Please do not implement anything yet. This is an audit only.
```
