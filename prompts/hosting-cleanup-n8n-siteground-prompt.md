# Hosting Cleanup And n8n SiteGround Prompt

Use this prompt in a new Codex chat named something like:

`Hosting Cleanup + n8n Installation`

```text
We are working on Buzzooka hosting cleanup and possible n8n setup for ClinicPilot X. Please treat this as a separate infrastructure/hosting chat, not the main ClinicPilot X product build chat.

Important project context:

- ClinicPilot X is a Buzzooka-owned product.
- Active local project folder:
  D:\BUZZOOKA WORKSPACE\Products\ClinicPilot X
- Old/archive folders with “Old” or “(Old)” in the name should be ignored unless I explicitly ask you to inspect them.
- GitHub should hold code and project memory.
- Google Drive should hold heavy files and backups.
- D drive should hold the portable working mirror.
- Office PC and travel laptop are just controllers/workstations.

Goal of this chat:

1. Audit my current SiteGround hosting account.
2. Identify what websites, files, databases, emails, domains, and old installs are currently there.
3. Do not delete anything without explicit approval.
4. Determine whether SiteGround can safely host a self-hosted n8n instance for ClinicPilot X.
5. If SiteGround is not suitable for n8n, recommend the cheapest stable alternative.
6. If an old Hostinger n8n instance still exists, help determine whether its workflows can be exported before the account disappears.
7. Prepare a migration/setup plan for n8n workflows related to ClinicPilot X.

ClinicPilot X automation context:

The MVP automation should support:

- inbound email or form inquiry capture
- lead classification: credible lead, spam, unsure, existing client, vendor/solicitation
- lead data extraction
- saving the lead to the app/backend
- notifying the business owner by email
- optional draft reply generation
- manual review queue for unsure messages

Please inspect first and make an inventory before changing anything.

Questions to answer:

1. What type of SiteGround hosting plan is this: shared hosting, cloud, VPS, or something else?
2. Does it support the requirements for n8n, such as long-running Node.js processes, Docker, persistent storage, HTTPS, cron/process management, and environment variables?
3. Are there existing websites or databases that should be preserved?
4. Are there old projects that can be archived?
5. Can n8n run reliably there, or would it be fragile?
6. What is the cheapest reliable hosting option if SiteGround is not a good fit?
7. What credentials, exports, or screenshots do you need from me?

Operating rules:

- Do not ask me to paste passwords into chat.
- If login is needed, open the correct login page or tell me exactly where to log in.
- Do not delete, overwrite, or migrate anything until you have made an inventory and I approve the specific action.
- Save any important findings into the ClinicPilot X project folder when relevant:
  D:\BUZZOOKA WORKSPACE\Products\ClinicPilot X\04-automations
  D:\BUZZOOKA WORKSPACE\Products\ClinicPilot X\05-backend-data
  D:\BUZZOOKA WORKSPACE\Products\ClinicPilot X\00-admin
```
