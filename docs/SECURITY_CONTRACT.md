# Security and Product Contract

This document is the non-negotiable baseline for all code in this repository.

## Core Principle

Build for a secure multi-tenant SaaS from day one, including during UI-only phases. Do not introduce shortcuts that increase future risk.

## Tenant Ownership Standard

- `organizationId` is the canonical tenant ownership field for code and database schemas.
- `workspace` may be used as product/UI language later, but ownership and authorization boundaries remain keyed by `organizationId`.
- Do not mix `workspaceId` and `organizationId` in implementation unless there is explicit, documented justification.

## Required Capabilities (Future-Ready by Design)

- Authentication
- Organization/workspace isolation
- Role-based access control (RBAC)
- Billing/subscription gates
- Payment webhook processing
- Email flows (invites, reset, notifications)
- Audit logging
- Secure environment variable handling
- Tenant-scoped product data

## Application Security Baseline

- Validate and sanitize all untrusted server inputs for every server action and endpoint.
- Protect auth-sensitive flows with CSRF defenses and secure session cookie behavior.
- Apply rate limiting and abuse controls to auth, invite, reset password, billing, upload, and webhook-adjacent endpoints.
- Apply secure HTTP headers where applicable.
- Maintain dependency hygiene: avoid unnecessary packages and keep dependency footprint minimal.

## Security Rules

- Never commit secrets, API keys, tokens, `.env` files, Stripe keys, Resend keys, database URLs, or private credentials.
- Commit only placeholder variable names in `.env.example`.
- Scope all product data and queries by `organizationId`.
- Never trust `organizationId`, `userId`, role, plan, price, or billing status from client payloads.
- Enforce permissions and business authorization server-side.
- Validate all server-side request/action inputs before authorization and persistence logic.
- Enforce CSRF protections and secure cookie settings on auth-sensitive routes and actions.
- Enforce rate limiting on auth, invite, reset password, billing, upload, and webhook-adjacent endpoints.
- Use secure headers where applicable for deployed surfaces.
- Avoid adding unnecessary dependencies; prefer minimal, maintained packages.
- Verify Stripe webhook signatures and process events idempotently.
- Derive billing access from server-side subscription state, never client UI state.
- Store reset/invite/email tokens securely with expiration.
- Authorize uploads server-side and use signed URLs.
- Never log secrets or sensitive customer data.

## Multi-Tenant Data Contract

- Every tenant-owned record must include `organizationId`.
- Server queries must filter by tenant scope by default.
- Cross-tenant reads/writes are forbidden unless explicitly approved and audited for platform admin flows.
- IDs from the client are treated as untrusted input and revalidated against authenticated tenant context.

## Auth and Access Contract

- Authentication identifies user identity.
- Authorization determines allowed action in tenant context.
- Role evaluation happens server-side against trusted data.
- UI visibility rules are convenience only; server checks are the source of truth.

## Billing Contract

- Pricing, plan, and entitlement state are server-owned.
- Webhook handlers must:
  - verify signature,
  - deduplicate events (idempotency),
  - safely handle retries and out-of-order delivery,
  - record auditable outcomes.
- Product access gates must read trusted subscription state from server-side storage.

## Email and Token Contract

- Generate cryptographically strong, single-purpose tokens.
- Hash or otherwise securely store token material.
- Enforce expiration and one-time use where applicable.
- Avoid token values in logs or analytics.

## Observability and Logs

- Use structured logs with tenant-safe metadata.
- Redact secrets and sensitive personal/customer content.
- Preserve audit trail integrity for security-sensitive actions.

## Environment and Secret Handling

- Keep secrets in environment variables or approved secret managers only.
- Never hardcode keys/tokens in source files.
- Rotate compromised credentials immediately.
- Keep `.env*` ignored by git, except `.env.example`.

## UI Direction and Licensing

- Follow Flowbite/Flowbite Pro visual style and component patterns where appropriate.
- Keep repository private while paid/proprietary Flowbite Pro code is present.
- Do not repurpose this repository into a public theme/template/UI kit.
- Keep UI clean, B2B SaaS-oriented, and maintainable.

## Product and Architecture Direction

- Keep SaaS Core separate from future product modules.
- Do not introduce niche-specific assumptions yet.
- Do not connect this project to Nuvio.

## Change Acceptance Gate

A change is not acceptable if it:

- weakens tenant isolation boundaries,
- shifts trust to client-provided auth/billing context,
- introduces secret exposure risk,
- bypasses server-side authorization,
- couples SaaS Core to niche module behavior prematurely.
