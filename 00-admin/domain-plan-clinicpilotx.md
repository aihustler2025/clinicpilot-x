# Domain Plan: clinicpilotx.com

Updated: 2026-05-22

## Domain

`clinicpilotx.com`

Registrar:

GoDaddy

Target:

Lovable project `37666967-bc8e-4032-9043-f45713e2bc22`

## Safe Setup Order

1. In Lovable, go to Project -> Settings -> Domains.
2. Add `clinicpilotx.com`.
3. Let Lovable generate the required DNS records.
4. In GoDaddy DNS, add exactly the records Lovable gives.
5. Check whether Lovable also requires `www.clinicpilotx.com` to be added separately.
6. Remove conflicting A, CNAME, or AAAA records only after reviewing them.
7. Wait for verification and SSL.
8. Set the primary domain after the domain is live.

## Important Notes From Lovable Docs

Lovable's custom domain documentation says domains from outside Lovable can be connected automatically through Entri or manually with DNS records supplied by Lovable. Manual setup can require A/TXT records, and advanced CDN/proxy setup can use CNAME records. Lovable warns that DNS changes can take up to 72 hours, and that conflicting `AAAA` records can cause the wrong site or stale routing.

Source: https://docs.lovable.dev/features/custom-domain

## Do Not Do Yet

- Do not point the domain to a guessed IP.
- Do not delete MX/SPF/DKIM/DMARC email records.
- Do not remove existing DNS records until they are inventoried.
- Do not enable Cloudflare/proxy behavior unless we intentionally choose that setup.
