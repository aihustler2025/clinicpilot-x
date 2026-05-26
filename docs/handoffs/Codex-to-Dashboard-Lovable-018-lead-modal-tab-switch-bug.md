# Codex to Dashboard Lovable 018: Lead Modal Closes When Switching Tabs

Mode: Build

Action requested: Fix the Add/Edit Lead modal so it does not close or lose entered data when the user switches browser tabs/windows or changes focus.

## Context

The owner and assistant are testing the Step 2A Leads module using the QA document.

Observed workflow:

1. Open `/leads`.
2. Click `Add Lead`.
3. The Add Lead modal opens.
4. Copy the full name from the QA document.
5. Paste the full name into the modal.
6. Switch back to the QA document to copy the email.
7. Return to ClinicPilot X.

Observed result:

- The Add Lead modal is gone.
- The assistant cannot complete the lead test.
- Any partially entered form data may be lost.

Expected result:

- Switching tabs/windows away from ClinicPilot X must not close the Add Lead modal.
- Returning to ClinicPilot X should show the modal still open with any typed/pasted values preserved.
- The modal should close only through explicit user intent, such as:
  - Clicking `Cancel`.
  - Clicking the close/X button.
  - Successfully saving the lead.
  - Pressing Escape, only if the form has no unsaved changes or after a confirmation if unsaved changes exist.

## Required Fix

Inspect `src/components/leads/LeadFormDialog.tsx` and any parent state in `src/pages/Leads.tsx`.

Likely areas to check:

- Dialog `onOpenChange` behavior.
- Radix/shadcn Dialog focus/blur handling.
- Any `onInteractOutside`, `onPointerDownOutside`, `onFocusOutside`, or route/state effect that closes the dialog.
- Any state reset triggered by window focus/visibility change or query refetch.
- React Query refetch-on-window-focus causing parent data/state to reset.

Recommended behavior:

- Prevent outside interaction or focus loss from closing the form while it has unsaved values.
- Preserve form state while the dialog is open.
- If React Query refetch on window focus is causing a remount/reset, adjust query or component state so the dialog is not closed by background refetch.
- Keep `Cancel`, close/X, and successful save behavior working.

## Scope Guardrails

Do not:

- Change database schema.
- Change RLS policies.
- Add fake production data.
- Start Step 2B.
- Change unrelated modules.
- Disable valid save/cancel behavior.

## Verification Required

Please verify these exact steps:

1. Open `/leads`.
2. Click `Add Lead`.
3. Type or paste `Sarah Johnson` into Full Name.
4. Switch to another browser tab/window or another app.
5. Return to ClinicPilot X.
6. Confirm the modal is still open.
7. Confirm `Sarah Johnson` is still in the Full Name field.
8. Paste the email `donjericho617+sarah-modal-test@gmail.com`.
9. Complete the required fields and save.
10. Confirm the lead appears in the Leads table.
11. Repeat with `Edit Lead`: open an existing lead, change Notes, switch away and back, confirm modal and typed notes persist.

## Response Back To Codex

Please respond with:

1. Summary
2. Root cause
3. Files changed
4. Verification performed
5. Any remaining risks

## Related Open Verification

Do not start Step 2B yet.

Codex still needs to verify:

- Handoff 016: Leads `Created` timestamp fix.
- Handoff 018: Add/Edit Lead modal tab-switch persistence fix.

