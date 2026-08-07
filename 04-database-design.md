# 04 — Database Design (v0.1, copied as-is — already well structured)

Maple Database Design

Version: 0.1

Purpose

This document defines the logical database design for Project Maple. It
is intended to guide development and will evolve before implementation.

Database Platform

-   PostgreSQL
-   Prisma ORM
-   Redis for cache, sessions, queues, and temporary data

Design Principles

-   Normalize core business data
-   Immutable financial ledger
-   Audit important changes
-   Soft delete where appropriate
-   UUID primary keys
-   Timestamp every major record
-   Index common search fields
-   Support multi-tenant operation

Core Domains

Marketplace

-   Marketplace
-   Theme
-   Branding
-   Configuration
-   Feature Flags

Users

-   Users
-   Profiles
-   Roles
-   Permissions
-   Sessions
-   OAuth Accounts
-   Trust Scores
-   Reputation
-   Verification Records

Geography

-   Countries
-   States/Provinces
-   Regions
-   Cities
-   Neighborhoods

Categories

-   Categories
-   Subcategories
-   Custom Fields
-   Category Rules

Advertisements

-   Listings
-   Listing Images
-   Listing Status History
-   Listing Promotions
-   Listing Analytics
-   Saved Listings
-   Favorites

Media

-   Uploaded Files
-   Image Variants
-   Watermark Jobs
-   Media Hashes
-   AI Moderation Results

Payments

-   Payment Providers
-   Invoices
-   Transactions
-   Marketplace Credits (“Gift Cards”)
-   Financial Ledger
-   Refunds
-   Promotion Purchases

Messaging

-   Conversations
-   Messages
-   Attachments
-   Notifications

Security

-   Audit Logs
-   Login History
-   Security Events
-   Block Lists
-   Allow Lists
-   Spam Events

Marketing

-   Campaigns
-   Coupons
-   Referral Program
-   Email Queue
-   Social Publishing Queue

Analytics

-   Site Metrics
-   Revenue Metrics
-   Category Metrics
-   Geographic Metrics
-   User Metrics

Relationships

-   One Marketplace -> Many Users
-   One Marketplace -> Many Listings
-   One User -> Many Listings
-   One Listing -> Many Images
-   One Listing -> Many Payments (promotion history)
-   One User -> Many Transactions
-   One Category -> Many Listings
-   One City -> Many Listings

Future Expansion

Reserve space for: - AI Assistant data - Plugin data - Workflow engine -
Federation between Maple deployments

Version History

0.1 - Initial logical database blueprint.
