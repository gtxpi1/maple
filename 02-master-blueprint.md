# 02 — Master Blueprint (v0.1, reorganized)

*Owns: vision framing, tech stack, feature list, v1.0 scope. Component
detail and data flow have moved to 03 — System Architecture to remove
duplication with the original architecture.txt.*

## Technology Stack

| Layer | Choice |
|---|---|
| Frontend | TypeScript, React, Responsive Design, PWA support |
| Backend | Node.js, TypeScript, REST API, WebSocket support, modular architecture |
| Database | PostgreSQL, Prisma ORM, Redis cache |
| OS | Ubuntu Linux Server |
| Deployment | Docker containers, one-command installer, automatic updates, automatic backups |

## Core Modules

- Maple Core, Maple Admin, Maple Shield (Security), Maple Media, Maple Pay,
  Maple Promotions, Maple AI, Maple Geo, Maple Config, Maple Themes

## Marketplace Features (Multi-Tenant)

- Multi-tenant architecture, multiple branded marketplaces, shared backend/services
- Independent per-tenant: branding, pricing, moderation, themes, payment options

## Analytics Scope

Revenue, countries, cities, user growth, popular categories, ad performance,
marketing effectiveness, system health, security alerts.

## User System

- Login: Email, Google, Apple, Microsoft
- Phone verification (optional)
- Trust score, reputation score, admin verification

## Advertisement System

Each listing has: permanent Ad ID, User ID, category, geographic location,
creation date, update history, promotion history, payment history,
analytics, status history.

## Design Goals

Fast, clean, mobile-first, low learning curve, familiar navigation patterns,
original branding/implementation, enterprise-grade security, everything
configurable from the admin panel.

## Version 1.0 Goals

User accounts, categories, ad posting, image uploads, search, messaging,
payments, admin panel, security, analytics.

*(See 20 — Product Roadmap [not yet written] for phasing beyond this list.)*
