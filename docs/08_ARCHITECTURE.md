# ARCHITECTURE

Version: 1.0

---

# PURPOSE

This document defines the complete technical architecture of the project.

The architecture must be modular, scalable, maintainable and production-ready.

Every implementation decision must follow this specification.

---

# ARCHITECTURE PRINCIPLES

The project must follow:

- Clean Architecture
- Feature First Architecture
- SOLID
- DRY
- KISS
- Composition over Inheritance
- Dependency Injection
- Separation of Concerns

Business logic must never depend on UI.

Infrastructure must be replaceable.

---

# PROJECT STRUCTURE

The project is a monorepository.

```

dating-miniapp/

│

├── backend/

├── frontend/

├── admin/

├── bot/

├── packages/

├── docker/

├── docs/

├── scripts/

├── .github/

├── .husky/

└── README.md

```

---

# TECHNOLOGY STACK

## Frontend

React

TypeScript

Vite

TailwindCSS

Telegram Mini Apps SDK

TanStack Router

TanStack Query

Zustand

React Hook Form

Framer Motion

Axios

Zod

---

## Backend

NestJS

TypeScript

Prisma ORM

PostgreSQL

Redis

JWT

Passport

Swagger

BullMQ (future-ready)

---

## Telegram Bot

grammY

TypeScript

Webhook mode

---

## Admin Panel

React

TypeScript

Vite

TanStack Query

TailwindCSS

React Hook Form

---

# DATABASE

PostgreSQL

Prisma ORM

UUID primary keys

Soft Delete

Automatic migrations

Seed support

---

# CACHE

Redis

Purpose:

Sessions

Rate Limiting

Temporary Storage

Future Queues

Future Notifications

---

# FILE STORAGE

Current implementation:

Local filesystem

/uploads

/photos

/videos

/thumbnails

Storage layer must be abstracted.

Future providers:

Amazon S3

Cloudflare R2

MinIO

---

# BACKEND STRUCTURE

```

src/

app/

auth/

users/

profile/

media/

likes/

matches/

reports/

cities/

interests/

notifications/

settings/

admin/

database/

common/

config/

middlewares/

guards/

filters/

interceptors/

pipes/

utils/

```

Each module is fully isolated.

---

# FRONTEND STRUCTURE

```

src/

app/

pages/

components/

features/

hooks/

services/

stores/

types/

utils/

styles/

assets/

```

Feature-based organization.

Shared components separated from business features.

---

# ADMIN STRUCTURE

```

src/

pages/

components/

features/

hooks/

services/

layouts/

stores/

types/

utils/

```

---

# BOT STRUCTURE

```

src/

commands/

middlewares/

handlers/

notifications/

services/

utils/

```

---

# SHARED PACKAGES

packages/

Contains reusable code.

Examples:

Shared Types

Validation Schemas

Constants

Enums

Utilities

API Client

Shared UI Tokens

---

# API LAYER

Frontend

↓

Axios Client

↓

Backend REST API

↓

Services

↓

Repositories

↓

Prisma

↓

PostgreSQL

---

# AUTHENTICATION FLOW

Telegram Mini Apps

↓

Validate InitData

↓

Create JWT

↓

Store Session

↓

Authorize Requests

↓

Refresh Token

↓

Logout

---

# AUTHORIZATION

User

Moderator

Administrator

Permissions checked on backend only.

Frontend never decides permissions.

---

# CONFIGURATION

Every environment variable stored in:

.env

.env.local

.env.production

.env.example

Never hardcode secrets.

---

# LOGGING

Structured logging.

Levels:

Debug

Info

Warn

Error

Logs must include:

Timestamp

Request ID

User ID (if available)

Execution Time

IP Address

---

# ERROR HANDLING

Global Exception Filter.

Standardized API errors.

Unexpected exceptions logged.

Sensitive information never returned.

---

# VALIDATION

Backend

ValidationPipe

DTO

class-validator

class-transformer

Frontend

Zod

React Hook Form

---

# SECURITY LAYERS

Telegram Validation

JWT

Role Validation

Rate Limiting

Helmet

CORS

Compression

Input Validation

Output Sanitization

Password Hashing (Admin)

---

# STATE MANAGEMENT

Frontend

Server State

↓

TanStack Query

Client State

↓

Zustand

Forms

↓

React Hook Form

---

# MEDIA PIPELINE

Upload

↓

Validation

↓

Compression

↓

Thumbnail Generation

↓

Storage

↓

Database Metadata

↓

Delivery

---

# MATCH FLOW

Like

↓

Store Like

↓

Check Reverse Like

↓

Create Match

↓

Create Notifications

↓

Telegram Bot Notification

↓

User Opens Telegram Chat

---

# ONLINE STATUS

Mini App Open

↓

Heartbeat

↓

Redis

↓

Database Update

↓

Online Indicator

↓

Close

↓

Last Seen Timestamp

---

# NOTIFICATIONS

Backend Event

↓

Notification Service

↓

Telegram Bot

↓

Delivery Status

↓

Notification History

---

# DEPENDENCY INJECTION

All services use NestJS Dependency Injection.

No static service instances.

No global mutable state.

---

# TESTING ARCHITECTURE

Unit Tests

↓

Integration Tests

↓

E2E Tests

↓

Build Verification

↓

Deployment

---

# CI/CD

GitHub Actions

Pipeline

Lint

↓

Type Check

↓

Unit Tests

↓

Integration Tests

↓

Build

↓

Docker Build

↓

Artifact Validation

---

# DEPLOYMENT

Ubuntu Linux

Docker Compose

Nginx

HTTPS

Automatic Restart

Health Checks

---

# SCALABILITY

Architecture must support future implementation of:

Premium

Subscriptions

Payments

Cloud Storage

CDN

Microservices

WebSockets

AI Moderation

Push Notifications

Stories

Messaging

Voice Calls

Video Calls

Multiple Countries

Multiple Languages

Without requiring a major refactor.

---

# CODING REQUIREMENTS

Every module must:

Be isolated.

Contain its own tests.

Contain DTOs.

Contain validation.

Contain documentation.

Expose only public interfaces.

Avoid circular dependencies.

---

# DEFINITION OF DONE

The architecture is considered complete when:

- Every component follows the defined structure.
- All modules are isolated.
- Clean Architecture principles are respected.
- The project builds successfully.
- Docker deployment works.
- Environment configuration is complete.
- No architectural violations exist.
- The project is ready for long-term maintenance and future expansion.
