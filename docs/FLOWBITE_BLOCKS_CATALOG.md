# Flowbite Pro Blocks Catalog

## Purpose

This file indexes the private local Flowbite Pro reference bank used by LaunchBase.
It is a path-and-notes catalog only.
Do not paste proprietary Flowbite Pro source code into this document.

## Reference Bank Rules

- Raw reference blocks must live only under `.flowbite-pro-reference/raw/`.
- `.flowbite-pro-reference/` must remain gitignored.
- This folder is private licensed reference material and is not part of runtime app code.
- Future UI implementation should select approved blocks from this bank before adapting code to `src/`.

## Reference Status (Phase 1c.2)

- Reference root found: `.flowbite-pro-reference/raw/`
- Placeholder format: `.svelte` files with category/block metadata comments only
- No proprietary source is stored in this catalog

## Block Bank Index

### P1 Foundation

- `.flowbite-pro-reference/raw/p1-foundation/application-ui/application-shells/` (8)
- `.flowbite-pro-reference/raw/p1-foundation/application-ui/side-navigations/` (12)
- `.flowbite-pro-reference/raw/p1-foundation/application-ui/dashboard-navbars/` (6)
- `.flowbite-pro-reference/raw/p1-foundation/application-ui/dashboard-footers/` (7)
- `.flowbite-pro-reference/raw/p1-foundation/application-ui/dashboard-cards-widgets/` (README only)
- `.flowbite-pro-reference/raw/p1-foundation/application-ui/empty-states/` (README only)
- `.flowbite-pro-reference/raw/p1-foundation/marketing-ui/headers/` (8)
- `.flowbite-pro-reference/raw/p1-foundation/marketing-ui/footer-sections/` (7)
- `.flowbite-pro-reference/raw/p1-foundation/marketing-ui/hero-sections/` (18)
- `.flowbite-pro-reference/raw/p1-foundation/marketing-ui/pricing-tables/` (7)
- `.flowbite-pro-reference/raw/p1-foundation/marketing-ui/feature-sections/` (10)
- `.flowbite-pro-reference/raw/p1-foundation/marketing-ui/cta-sections/` (10)
- `.flowbite-pro-reference/raw/p1-foundation/marketing-ui/faq-sections/` (5)
- `.flowbite-pro-reference/raw/p1-foundation/marketing-ui/testimonials/` (5)
- `.flowbite-pro-reference/raw/p1-foundation/marketing-ui/customer-logos/` (5)
- `.flowbite-pro-reference/raw/p1-foundation/auth-ui/login-forms/` (5)
- `.flowbite-pro-reference/raw/p1-foundation/auth-ui/register-forms/` (5)
- `.flowbite-pro-reference/raw/p1-foundation/auth-ui/reset-password-forms/` (5)
- `.flowbite-pro-reference/raw/p1-foundation/auth-ui/account-recovery/` (5)

### P2 Product Modules

- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/advanced-tables/` (7)
- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/table-headers/` (13)
- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/table-footers/` (6)
- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/dropdown-filters/` (8)
- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/crud-layouts/` (6)
- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/create-forms/` (5)
- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/update-forms/` (5)
- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/read-sections/` (6)
- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/create-modals/` (7)
- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/update-modals/` (7)
- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/read-modals/` (6)
- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/delete-confirm/` (6)
- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/create-drawers/` (5)
- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/update-drawers/` (5)
- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/read-drawers/` (6)
- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/success-message/` (5)
- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/faceted-search-modals/` (5)
- `.flowbite-pro-reference/raw/p2-product-modules/application-ui/faceted-search-drawers/` (4)

### P3 Support Pages

- `.flowbite-pro-reference/raw/p3-support-pages/marketing-ui/404-pages/` (3)
- `.flowbite-pro-reference/raw/p3-support-pages/marketing-ui/500-pages/` (3)
- `.flowbite-pro-reference/raw/p3-support-pages/marketing-ui/maintenance-pages/` (3)
- `.flowbite-pro-reference/raw/p3-support-pages/marketing-ui/cookie-consent/` (4)
- `.flowbite-pro-reference/raw/p3-support-pages/marketing-ui/newsletter-sections/` (5)
- `.flowbite-pro-reference/raw/p3-support-pages/marketing-ui/contact-forms/` (6)
- `.flowbite-pro-reference/raw/p3-support-pages/marketing-ui/banners/` (5)
- `.flowbite-pro-reference/raw/p3-support-pages/marketing-ui/popups/` (5)

## Best Candidate Mappings For Current App Surfaces

- App shell, sidebar, topbar:
  - `p1-foundation/application-ui/application-shells/`
  - `p1-foundation/application-ui/side-navigations/`
  - `p1-foundation/application-ui/dashboard-navbars/`
  - `p1-foundation/application-ui/dashboard-footers/`
- Login page:
  - `p1-foundation/auth-ui/login-forms/`
  - optional recovery actions from `p1-foundation/auth-ui/account-recovery/`
- Signup page:
  - `p1-foundation/auth-ui/register-forms/`
- Pricing page:
  - `p1-foundation/marketing-ui/pricing-tables/`
  - plus supporting `hero-sections`, `cta-sections`, `faq-sections`, `testimonials`
- Dashboard placeholder and empty state:
  - `p1-foundation/application-ui/dashboard-cards-widgets/`
  - `p1-foundation/application-ui/empty-states/`
- Settings page:
  - `p2-product-modules/application-ui/crud-layouts/`
  - `p2-product-modules/application-ui/read-sections/`
  - `p2-product-modules/application-ui/update-forms/`
- Tables/forms/cards for future app modules:
  - `p2-product-modules/application-ui/advanced-tables/`
  - `table-headers/`, `table-footers/`, `dropdown-filters/`
  - `create-forms/`, `update-forms/`, `create-modals/`, `update-modals/`, `create-drawers/`, `update-drawers/`

## Notes

- This catalog intentionally stores only paths, category names, counts, and short usage notes.
- Keep repository private while any Flowbite Pro licensed material exists in `.flowbite-pro-reference/`.
