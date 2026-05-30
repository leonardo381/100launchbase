# Engineering Checklist

Use this checklist before merging any change.

## Security Baseline

- No secrets, tokens, private keys, `.env`, or credential values were added to git.
- New environment variables were added as names only in `.env.example`.
- Logs do not expose secrets or sensitive customer data.
- All server inputs are validated and sanitized before business logic runs.
- Session and cookie behavior is secure for auth-sensitive flows.
- Auth-sensitive routes/actions include abuse protections (for example, rate limiting and lockout controls where appropriate).
- No unnecessary package was added; dependency additions are justified and maintained.

## Tenant Isolation

- Any new tenant-owned data includes `organizationId`.
- Reads/writes are tenant-scoped server-side.
- Client-provided tenant/user context is treated as untrusted and revalidated.

## Auth and RBAC

- Authorization checks are implemented server-side.
- Client UI checks are not used as security controls.
- Role and permission decisions come from trusted server state.

## Billing and Entitlements

- Access gates depend on server-side subscription state.
- No plan/price/billing trust from client payloads.
- Webhook-related code verifies signatures and is idempotent.

## Email, Tokens, and Uploads

- Security-sensitive tokens are time-limited and stored securely.
- Upload flows require server authorization and signed URLs.

## Architecture and Product Direction

- SaaS Core remains separated from product modules.
- No niche product assumptions were introduced.
- No integration or coupling with Nuvio was added.

## UI and Repository Policy

- UI stays clean, maintainable, and B2B SaaS-oriented.
- Flowbite/Flowbite Pro usage stays within private repository constraints.
- No steps were taken toward publishing this as a template/theme/UI kit.
