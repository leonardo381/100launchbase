# Launchbase

Security-first SaaS foundation built with SvelteKit.

## Project Contract

This project follows a strict security and product contract from day one:

- Auth, tenant isolation, RBAC, billing gates, and auditable actions are first-class architecture concerns.
- No shortcuts that make future tenant isolation, payment security, or access control harder.
- All sensitive checks are server-side; client state is never treated as trusted authority.
- No secrets in git, ever. Use `.env.example` placeholders only.

Read these docs before implementing features:

- [Security Contract](docs/SECURITY_CONTRACT.md)
- [Engineering Checklist](docs/ENGINEERING_CHECKLIST.md)

## Local Development

```sh
npm install
npm run dev
```

## Build

```sh
npm run build
npm run preview
```

## UI and Licensing Direction

- Use Flowbite or Flowbite Pro style/components where appropriate.
- Keep this repository private while using paid/proprietary Flowbite Pro assets.
- Do not convert this codebase into a public UI kit, template, or theme product.

## Architecture Direction

- Keep SaaS Core separate from future product modules.
- Avoid niche-specific product assumptions at this stage.
- Do not connect this project to Nuvio.
