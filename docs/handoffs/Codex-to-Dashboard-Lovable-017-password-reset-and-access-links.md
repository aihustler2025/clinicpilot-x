# Codex to Dashboard Lovable 017: Password Reset Bug and Access Links

Mode: Build

Action requested: Fix the password reset/recovery flow, verify it, and report back with exact access links.

## Context

The owner is trying to reset the admin account password for:

`donjericho617@gmail.com`

The owner requested a password reset email from the app/Supabase, opened the reset email, clicked the Supabase password reset link, reached the app's `Set a new password` screen, entered a new password, and clicked `Update password`.

Observed result:

`Error: Auth session missing!`

This blocks the owner from reliably resetting the admin account and from giving the assistant clear login instructions for testing.

## Related Current App Links

Current Dashboard Lovable preview:

`https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app`

Current auth page:

`https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app/auth`

The app is not yet published to the production custom domain.

## What Is Likely Wrong

The reset page is rendering, but the app is not successfully establishing or preserving the Supabase recovery session before calling the password update method.

Please inspect for:

- Supabase recovery URL callback handling.
- Whether the reset route receives a `code`, access token hash, or recovery parameters.
- Whether `supabase.auth.exchangeCodeForSession(...)` is needed for code-based recovery links.
- Whether `supabase.auth.onAuthStateChange(...)` is handling `PASSWORD_RECOVERY`.
- Whether the app strips query/hash params too early.
- Whether reset links are opening on a URL that is not included in Supabase Auth redirect allow-list settings.
- Whether Supabase Auth settings need `Site URL` and `Redirect URLs` updated for the Lovable preview and later custom domain.

## Required Fix

Make password reset work end-to-end from the real email link.

The flow should be:

1. User requests password reset from `/auth`.
2. User clicks the reset link in the email.
3. User lands on the app reset password screen.
4. App detects/exchanges the recovery session correctly.
5. User enters new password and confirmation.
6. Password updates successfully.
7. User is redirected to `/auth` or the dashboard with a success message.
8. User can sign in with the new password.

## Scope Guardrails

Do not:

- Ask the owner to share passwords in chat.
- Hardcode a password.
- Disable auth security broadly.
- Change RLS policies.
- Start Step 2B.
- Change unrelated dashboard modules.

Small Supabase Auth config instructions are allowed if the owner must update them manually in Supabase, but please be exact.

## Access Links Needed In Your Response

Please include the exact links the owner should use:

1. Admin/staff login URL.
2. Public preview/root URL.
3. Password reset request URL or instructions.
4. Any future production-domain URL that should be used after `clinicpilotx.com` is connected.

Important clarification:

- Admin and staff should use the same login URL.
- Role-based access should be determined after login by Supabase roles/RLS, not by separate login pages unless the app intentionally has separate portals.

## Verification Required

Please verify the fix with a test account or explain exactly what the owner must do to verify if email inbox access is required.

At minimum, report:

1. Files changed.
2. Root cause.
3. Whether Supabase Auth redirect allow-list changes are needed.
4. Exact redirect URL(s) to add if needed.
5. Exact user-facing login/reset links.
6. Whether the owner should retry the password reset after the change.

## Also Acknowledge Previous Handoff 016

Dashboard Lovable reported that the Leads timestamp bug was fixed by parsing `leads.created_at` as UTC.

Codex has not yet completed live UI verification of that fix. Do not start Step 2B until Codex verifies both:

- Handoff 016 timestamp fix.
- This handoff 017 password reset fix.

