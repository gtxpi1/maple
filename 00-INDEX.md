# Project Maple — Design Library (Reorganized v0.2)

Master index for all design, architecture, and development documentation.
Reorganized from source docs on 2026-08-07 so the set can drive implementation.

| # | Document | Status | Source |
|---|----------|--------|--------|
| 01 | Vision & Mission | Drafted (from Blueprint) | blueprint.txt |
| 02 | Master Blueprint | Complete | blueprint.txt |
| 03 | System Architecture | Complete | architecture.txt |
| 04 | Database Design | Complete | maple_database_design.txt |
| 05 | API Specification | Complete | maple_api_specification.txt |
| 06 | Admin Panel Design | Complete | maple_admin_panel_design.txt |
| 07 | Security Architecture | Complete | maple_security_architecture.txt |
| 08 | UI/UX Design Guide | Complete | maple_ui_ux_design.txt |
| 09 | Development Standards | Complete | maple_development_standards.txt |
| 10 | Deployment Guide | Complete | maple_deployment_guide.txt |
| 11 | Testing Strategy | Complete | maple_testing_strategy.txt |
| 12 | Plugin Architecture | **Not yet written** | — |
| 13 | Media Engine Design | Complete | maple_media_engine_design.txt |
| 14 | Payment Engine Design | Complete | maple_payment_engine_design.txt |
| 15 | AI Operations Design | Complete | maple_ai_operations_design.txt |
| 16 | Promotion Engine Design | **Not yet written** | — |
| 17 | Geographic Manager Design | **Not yet written** | — |
| 18 | Configuration Manager Design | **Not yet written** | — |
| 19 | Analytics & Reporting Design | **Not yet written** | — |
| 20 | Product Roadmap | **Not yet written** | — |

## What Changed in This Pass

- Merged duplicate content between `blueprint.txt` and `architecture.txt` — Blueprint now owns vision/stack/features, Architecture now owns components/data flow/scaling.
- Every "Planned" status from the old library that had a corresponding source file is now marked **Complete** and expanded into full sections (Purpose, Scope, Detail, Open Questions).
- Five documents referenced in the original index (12, 16–20) still have no source content. These are the actual gaps before a full build can start — see each stub file for what's needed.
- Added a **Build Readiness** section at the bottom of this index.

## Reading Order for Implementation

1. Vision & Blueprint (01–02) — what we're building and why
2. System Architecture (03) — component map
3. Database Design (04) — schema foundation everything else depends on
4. API Specification (05) — contract between frontend/backend
5. Security Architecture (07) + Development Standards (09) — non-negotiables baked in from commit #1
6. Domain engines (13–15, and the missing 12/16–18) — feature-by-feature build order
7. Admin Panel (06) + UI/UX (08) — surfaces
8. Testing (11) + Deployment (10) — how it ships

## Build Readiness

**Ready to scaffold now:** repo structure, Prisma schema (04), core REST API skeleton (05), auth + security middleware (07), CI/lint setup (09).

**Blocking gaps before feature-complete build:**
- No Plugin Architecture (12) — Admin Panel and Blueprint both assume a Plugin Manager exists.
- No Promotion Engine Design (16) — Database and Blueprint reference `Listing Promotions` / `Promotion Purchases` with no defined rules, pricing, or lifecycle.
- No Geographic Manager Design (17) — Database has a full Geography domain (Countries → Neighborhoods) but no defined admin workflow or API behavior.
- No Configuration Manager Design (18) — Architecture repeatedly says "everything configurable, importable/exportable/versioned" but the mechanism is undefined.
- No Analytics & Reporting Design (19) — Blueprint and Database both list analytics fields; no defined pipeline, storage, or dashboard spec.
- No Product Roadmap (20) — no phasing/milestones beyond "Version 1.0 Goals" in the Blueprint.

Recommendation: scaffold the core (auth, listings, categories, geo, media, search) in parallel with writing 12/16–20, since those five feed directly into Admin Panel and Payment Engine work that's already spec'd.
