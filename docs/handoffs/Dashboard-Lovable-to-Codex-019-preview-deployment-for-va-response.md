# Dashboard Lovable to Codex 019: Preview Deployment for VA Response

Date received: 2026-05-26

Source file from owner:

- `C:\Users\Rosstafari\Downloads\DASHBOARD LOVABLE TO CODEX 13.docx`

## Summary From Lovable

Dashboard Lovable confirms that the handoff 018 Add/Edit Lead modal fix exists in the current preview build.

Current preview URL containing the fix:

`https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app`

Published URL:

- None.
- `is_published: false`.
- The project has never been published.

## Publish Guidance

Lovable recommends not publishing just to test this fix.

For Step 2A QA, the preview URL is the correct testing surface.

Publishing should be reserved for when Codex has signed off on handoffs 016, 017, and 018 and the owner is ready to create a production build.

## Likely VA Issue

The VA is likely using:

- A stale cached preview tab.
- A URL that is not the current preview URL.
- A preview access mode that does not support full authenticated CRUD.

Lovable says preview reflects latest committed code automatically, but preview URLs may require Lovable login by default.

Best QA access path:

- Invite the VA as a collaborator via Lovable `Share -> invite collaborator`.

Alternative:

- Generate a `Share preview link`, but Lovable warns this may be view-only and may not support full authenticated CRUD testing.

## VA Refresh Steps

Lovable recommends:

1. Hard refresh `/leads`.
   - Windows/Linux: `Ctrl + Shift + R` or `Ctrl + F5`.
   - macOS: `Cmd + Shift + R`.
2. If still failing, close all ClinicPilot X tabs and reopen the current preview URL.
3. If still failing, open the preview URL in incognito/private mode and sign in again.

Lovable says sign out/sign in is not required for the handoff 018 fix because it is frontend-only.

## VA Verification Tell

On `/leads`:

1. Open `Add Lead`.
2. Type `Sarah Johnson`.
3. Switch tabs for 5+ seconds.
4. Return to ClinicPilot X.
5. Modal should remain open and name should remain.
6. Click outside the modal on the dim backdrop while the form has typed data.
7. Modal should not close.

If clicking the backdrop dismisses the modal with typed data, the VA is on a stale bundle.

## Optional Future Improvement

Lovable offered to add a small version/build stamp so VAs can confirm which bundle they are testing.

Codex recommendation: defer unless repeated stale-build confusion continues.

