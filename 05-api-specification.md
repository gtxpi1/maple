# 05 — API Specification (v0.1, reorganized)

## Purpose

Define all public/internal APIs.

## Sections (endpoints TBD per section)

Authentication API · Marketplace API · Listings API · Categories API ·
Geography API · Media Upload API · Search API · Messaging API · Payments
API · Promotion API · Analytics API · Admin API · AI Operations API ·
Webhooks

## Standards

- REST, JSON
- Versioned: `/api/v1`
- OAuth / JWT
- Rate limiting
- Audit logging
- Idempotent payment endpoints
- OpenAPI documentation (planned)

## Gaps to resolve before build

- No request/response schemas defined per endpoint yet — this doc lists
  sections only. Each section above needs its own contract before frontend
  work can start against it.
- No error-response format standard specified.
- No pagination/filtering convention specified for list endpoints
  (Listings, Search, Analytics).
