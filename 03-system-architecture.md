# 03 — System Architecture (v0.1, reorganized)

*Owns: component map, layer detail, data flow, security controls, scaling
path. Vision/stack/feature-list content has moved to 02 — Master Blueprint.*

## Architectural Goals

Modular, configurable, secure by default, multi-tenant, horizontally
scalable, API-first, high availability, Linux-first deployment, original
implementation with familiar usability.

## Layers

**Client Layer** — React + TypeScript web app, responsive desktop/mobile UI, PWA support.

**Edge Layer** — DNS/CDN, Cloudflare integration, TLS termination, DDoS
protection, bot protection, rate limiting.

**Application Layer** — Node.js + TypeScript. Services: Authentication,
Marketplace, Search, Messaging, Notification, Promotion, Media, Payment,
AI, Analytics, Administration. REST APIs + WebSocket services.

**Data Layer** — PostgreSQL (primary), Prisma ORM, Redis (cache/sessions/queues).

**Storage** — Images, thumbnails, watermarked images, configuration
backups, audit logs, database backups.

## Core Modules

Maple Core · Maple Admin · Maple Shield (Security) · Maple Media · Maple Pay
· Maple Promotions · Maple AI · Maple Geo · Maple Config · Maple Themes

## Multi-Tenant Design

One codebase powers multiple independent marketplaces. Each has: branding,
theme, categories, geographic coverage, pricing rules, payment options,
moderation settings, feature toggles.

## Configuration Philosophy

Nearly every feature is configurable: categories, themes, branding, auth
providers, promotions, payments, security rules, watermarks, geographic
hierarchy. Configurations are importable, exportable, versioned, validated,
and rollback-capable.

*(Mechanism for this is undefined — see 18: Configuration Manager Design, not yet written.)*

## Security Architecture (summary — full detail in 07)

Parameterized DB access, input validation, output encoding, CSRF
protection, secure session management, audit logging, threat monitoring,
configurable allow/block lists, word/spam filtering, Cloudflare + Linux
firewall integration.

## Media Pipeline (summary — full detail in 13)

Upload → Validation → Virus scan (future) → Metadata removal → Optimization
→ Watermark → Thumbnail generation → Storage.

## Payment Architecture (summary — full detail in 14)

Pluggable providers: credit card provider(s), Litecoin, marketplace credits.
Every transaction recorded in an immutable financial ledger.

## AI Operations (summary — full detail in 15)

AI assistant observes platform health, summarizes events, recommends
actions, integrates through a provider-abstraction API layer.

## Deployment (summary — full detail in 10)

Ubuntu Server, Docker containers, reverse proxy, automated backups,
one-command installer, health monitoring.

## Future Scaling

Multiple application servers, read replicas, object storage, search
cluster, background workers, central management hub for multiple Maple
deployments.
