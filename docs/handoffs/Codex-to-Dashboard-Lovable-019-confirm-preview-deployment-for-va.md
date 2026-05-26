# Codex to Dashboard Lovable 019: Confirm Preview Deployment for VA Testing

Mode: Plan

Action requested: Confirm deployment/preview status only. Do not change code unless you explicitly discover the 018 fix was not deployed.

## Context

Dashboard Lovable reported handoff 018 fixed the Add/Edit Lead modal tab-switch bug.

However, the owner's VA reports the bug still happens while testing.

The owner notes the project has not been formally published yet. This may mean the VA is testing a stale build, a different preview URL, or a published/public URL that has not received the latest editor changes.

## Need From Dashboard Lovable

Please answer these questions clearly:

1. What exact URL currently contains the handoff 018 fix?
2. Is the fix visible on this shared preview URL?

`https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app`

3. Does the owner need to click `Publish` before the VA can see this fix?
4. If yes, what exact URL should the owner give the VA after publishing?
5. If no, what exact URL should the VA use right now?
6. Is there any cache/session issue that requires the VA to hard refresh, open incognito, or sign out/sign back in?
7. Please confirm the expected test steps:
   - Open `/leads`.
   - Click `Add Lead`.
   - Type/paste a name.
   - Switch to another tab/window.
   - Return to ClinicPilot X.
   - Modal remains open and typed data remains.

## Guardrails

Do not:

- Start Step 2B.
- Change unrelated code.
- Add data.
- Change auth/RLS.
- Change domain/DNS.

This is a deployment visibility check so the owner and VA test the correct build.

