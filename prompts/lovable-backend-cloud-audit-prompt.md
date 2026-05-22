# Lovable Backend And Cloud Audit Prompt

Paste this into Lovable after the general audit if backend details are still unclear:

```text
For ClinicPilot X, please audit the current backend and hosting setup only. Do not make changes yet.

Please answer:

1. Is this project using Lovable Cloud, standalone Supabase, another Supabase project, or another backend?
2. If Supabase is used, is it managed through Lovable or connected as an external Supabase account?
3. Which database tables currently exist?
4. Which features depend on real database reads/writes?
5. Which screens are still mock/static data?
6. Is authentication active? If yes, what provider and roles are configured?
7. Are any edge functions, webhooks, storage buckets, or scheduled jobs configured?
8. Can this project be switched to Lovable Cloud without data loss?
9. What would break or need migration if we switch backend providers?
10. Can this project sync/export to GitHub? If yes, what repo is currently connected?

Please produce a plain technical handoff summary suitable for another developer or Codex agent.
```
