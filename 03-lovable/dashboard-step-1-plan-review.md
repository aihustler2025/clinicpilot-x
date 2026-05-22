# Dashboard Step 1 Plan Review

Updated: 2026-05-22

## Summary

Dashboard Lovable returned a Step 1 plan for security, auth, roles, and project memory. The plan is directionally correct and should be approved with clarifications.

## Good Parts

- Correctly scopes Step 1 to security/auth only.
- Drops public `Allow full access (testing)` policies.
- Adds `profiles`, `user_roles`, `has_role()`, and `is_staff()`.
- Adds Supabase email/password auth routes.
- Protects dashboard routes.
- Keeps domain, n8n, Stripe, Twilio, VAPI, and marketing merge out of Step 1.
- Includes testing and Supabase linter/security scan steps.

## Clarifications Needed Before Approval

1. Project memory should be real repo/source files where possible, not only Lovable memory/knowledge entries.
2. The first-user bootstrap should be safe and explicit. Ideally the owner/admin email should be configured/confirmed, and admin promotion should be done through a controlled SQL step, not an ambiguous automatic grant.
3. Public lead capture should be deferred to Step 2, but the plan should acknowledge that anonymous insert will eventually be allowed only through a restricted form/edge-function path, not broad table access.
4. Existing data should not be deleted or destructively migrated.
5. The implementation must report exact migration SQL/policy names after completion.

## Recommendation

Approve Step 1 only with the custom approval message in:

`prompts/lovable-dashboard-step-1-approve-with-guardrails.md`
