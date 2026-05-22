# Lovable Audit Prompt

Paste this into Lovable when ready:

```text
We are preparing a technical handoff/audit for the ClinicPilot X project. Please summarize the current project in a structured way:

1. List all pages/routes in the app.
2. Identify which pages are marketing/public and which are authenticated/dashboard pages.
3. Identify the backend/database currently used by this project.
4. List all database tables/collections/entities and their fields.
5. Identify which UI screens are connected to real data and which use mock/static data.
6. List all integrations currently configured.
7. Identify any environment variables or secrets required, without revealing secret values.
8. Explain the auth setup and user roles.
9. List known unfinished features or TODOs.
10. Explain whether this project can be exported or synced to GitHub.

Do not make changes yet. This is an audit only.
```
