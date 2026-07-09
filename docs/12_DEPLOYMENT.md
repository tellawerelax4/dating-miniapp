# DEPLOYMENT

Version: 1.0

---

# PURPOSE

This document describes how the project must be deployed in both development and production environments.

The deployment process must be fully automated and reproducible.

No manual configuration should be required after initial server preparation.

---

# DEPLOYMENT TARGET

Primary OS

Ubuntu Server LTS

Supported Architectures

- x86_64
- ARM64 (future compatible)

Deployment Method

Docker Compose

Reverse Proxy

Nginx

HTTPS

Let's Encrypt

---

# PROJECT STRUCTURE

The deployment must support the following services:

- Frontend
- Backend API
- Telegram Bot
- PostgreSQL
- Redis
- Admin Panel
- Nginx

All services must be isolated using Docker.

---

# DOCKER

Each application must have its own Dockerfile.

Required images:

frontend

backend

admin

bot

postgres

redis

nginx

---

# DOCKER COMPOSE

docker-compose.yml must include:

Frontend

Backend

Admin

Bot

PostgreSQL

Redis

Nginx

Volumes

Networks

Healthchecks

Restart Policies

Environment Variables

---

# ENVIRONMENT VARIABLES

Generate:

.env.example

.env.development

.env.production

Required variables include:

DATABASE_URL

REDIS_URL

BOT_TOKEN

JWT_SECRET

JWT_REFRESH_SECRET

ADMIN_USERNAME

ADMIN_PASSWORD

UPLOAD_PATH

PUBLIC_URL

API_URL

MINI_APP_URL

MAX_DAILY_LIKES

MAX_DAILY_REPORTS

MAX_VIDEO_DURATION

MAX_PHOTOS

NODE_ENV

PORT

LOG_LEVEL

---

# SERVER REQUIREMENTS

Minimum

2 CPU

4 GB RAM

40 GB SSD

Ubuntu LTS

Recommended

4 CPU

8 GB RAM

80 GB SSD

---

# REQUIRED SOFTWARE

Docker

Docker Compose

Git

Node.js (development only)

pnpm

Nginx

Certbot

---

# INSTALLATION

README must contain a complete step-by-step installation guide.

Including:

Clone repository

Install dependencies

Configure environment

Run migrations

Seed database

Start containers

Verify deployment

No undocumented steps are allowed.

---

# DATABASE

Deployment must automatically:

Create database

Run migrations

Run seed

Verify schema

No manual SQL commands required.

---

# FILE STORAGE

Create automatically:

uploads/

photos/

videos/

thumbnails/

Directories must be mounted as Docker volumes.

---

# NGINX

Responsibilities:

HTTPS

Reverse Proxy

Compression

Security Headers

Caching

Static File Delivery

Rate Limiting

---

# SSL

Automatically support:

Let's Encrypt

Automatic renewal

HTTPS redirect

Secure cookies

HSTS

---

# HEALTH CHECKS

Every service must expose health endpoints.

Backend

/api/v1/health

Frontend

HTTP 200

Bot

Heartbeat

Database

Connection test

Redis

PING

---

# LOGGING

Logs must be separated by service.

backend

frontend

admin

bot

nginx

Logs must support rotation.

---

# BACKUPS

Automatic database backup.

Configurable schedule.

Media backup support.

Restore procedure documented.

Retention configurable.

---

# UPDATE PROCESS

Deployment updates should require:

git pull

↓

docker compose build

↓

docker compose up -d

↓

automatic migration

↓

health verification

No manual rebuilds outside Docker.

---

# ROLLBACK

Document rollback procedure.

Rollback must support:

Application

Database

Docker images

Configuration

---

# MONITORING

Future-ready.

Architecture should support:

Prometheus

Grafana

Sentry

Uptime Kuma

Without major changes.

---

# SECURITY

Secrets stored only in environment variables.

Containers run with least privilege.

No unnecessary exposed ports.

Internal services isolated by Docker network.

---

# GITHUB

Repository must include:

.gitignore

.editorconfig

.gitattributes

LICENSE

README.md

Dependabot configuration

GitHub Actions

Issue Templates

Pull Request Template

CODEOWNERS

---

# CI/CD

GitHub Actions pipeline:

Install

↓

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

↓

Deploy (future-ready)

---

# README REQUIREMENTS

README.md must include:

Project Overview

Features

Technology Stack

Requirements

Installation

Environment Variables

Docker

Database

Development

Production

Deployment

Updating

Backup

Restore

Troubleshooting

FAQ

License

Project Structure

Terminal Commands

Common Errors

---

# TERMINAL COMMANDS

README must document every required command.

Examples include:

Repository setup

Dependency installation

Development mode

Production build

Database migration

Database seed

Docker build

Docker compose

Testing

Linting

Formatting

Type checking

Deployment

Rollback

Backup

Restore

---

# VALIDATION

Deployment is successful only if:

Backend starts.

Frontend starts.

Admin Panel starts.

Telegram Bot connects.

Database is initialized.

Redis is available.

Nginx serves HTTPS.

Media uploads work.

Health checks pass.

README instructions reproduce a working installation.

---

# DEFINITION OF DONE

Deployment is complete only when:

- A clean server can be fully configured using only the repository documentation.
- Docker deployment succeeds without manual fixes.
- All services communicate correctly.
- SSL is supported.
- Backups are documented.
- Updates are documented.
- Rollback is documented.
- No deployment step depends on undocumented knowledge.
