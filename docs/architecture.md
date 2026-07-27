# Architecture

> Source code is private/client-confidential. Architecture and implementation details are shared at a safe case-study level.

## System Boundary

LOOSH is a single-store e-commerce system with storefront and admin operations. The public case study focuses on safe product and architecture descriptions, not client source or private deployment data.

## Main Components

| Surface | Responsibility |
|---|---|
| Storefront | Product browsing, product details, cart, checkout, order confirmation, tracking, support surfaces |
| Admin dashboard | Product management, variants, inventory, delivery rules, settings, and order status operations |
| API backend | Auth/session handling, checkout, inventory transitions, order workflow, settings, and DTO boundaries |
| Database | Products, variants, inventory counts, order state, settings, and operational records |
| Static delivery | Built storefront artifact, headers, redirects, sitemap, robots, and canonical route handling |

## Public-Safe Stack Summary

- React, TypeScript, Vite, Tailwind CSS, React Router
- Node.js, Express, Prisma, PostgreSQL
- SEO metadata, sitemap, robots, JSON-LD
- CI/release verification and production deployment preparation

## Data Flow

1. Shopper selects a product and variant.
2. Cart and checkout preserve selected color/shade choices.
3. Checkout validates required details and creates a COD order.
4. Inventory reservations protect stock while the order is active.
5. Admin views order details and applies safe status transitions.
6. Tracking requires order reference and checkout phone number.
7. Owner/deployment handoff tracks production environment values outside public source.
