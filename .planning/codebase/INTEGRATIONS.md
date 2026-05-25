# External Integrations

**Analysis Date:** 2026-05-25

## Overview

This repository is a personal profile README (`README.md`) for developer **uzair zahari** (uz6r). No actual integration code, configuration, SDK clients, or environment variables are present in this repository. All integration information below is **declared in the README** as shipped work, primarily related to the developer's role at **courtsite** (a sports booking platform) and their side project **TracePace**.

## Payment Integrations

### KiplePay
- **Status:** Shipped (courtsite platform)
- **Purpose:** Payment processing for a sports booking platform (97k → 700k+ users)
- **Details per README:** Includes error handling, retry logic, transaction monitoring
- **Declared in:** `README.md` line 75
- **Config/Code:** Not present in this repository

### Spay Global
- **Status:** Shipped (courtsite platform)
- **Purpose:** Alternative payment gateway for sports bookings
- **Details per README:** Includes error handling, retry logic, transaction monitoring
- **Declared in:** `README.md` line 75
- **Config/Code:** Not present in this repository

## Tax & Compliance

### MyLHDN e-Invoice API
- **Status:** Shipped (courtsite platform)
- **Purpose:** Malaysian tax-compliant B2B2C automated invoicing via LHDN (Inland Revenue Board of Malaysia) e-invoice API
- **Declared in:** `README.md` line 77
- **Details:** Automated tax-compliant invoicing integration
- **Config/Code:** Not present in this repository

## Security & Bot Protection

### Cloudflare Turnstile
- **Status:** Shipped (courtsite platform)
- **Purpose:** Bot abuse prevention on booking forms (CAPTCHA replacement)
- **Declared in:** `README.md` line 78
- **Config/Code:** Not present in this repository

## Authentication & Identity

### JWT (JSON Web Tokens)
- **Status:** In use (presumably courtsite + TracePace)
- **Purpose:** Stateless authentication
- **Declared in:** `README.md` line 61 (badge)
- **Config/Code:** Not present in this repository

### OAuth 2.0
- **Status:** In use
- **Purpose:** Third-party authentication (Google provider inferred from Google badge styling)
- **Declared in:** `README.md` line 62 (badge)
- **Config/Code:** Not present in this repository

## Observability

### Sentry
- **Status:** In use (presumably courtsite + TracePace)
- **Purpose:** Error tracking, performance monitoring
- **Declared in:** `README.md` line 63 (badge)
- **Config/Code:** Not present in this repository

## TracePace-Specific Integrations

### Weather Integration
- **Status:** Planned / in development (TracePace v0.5.0-alpha)
- **Purpose:** Overlay weather data on GPS activity visualization posters
- **Declared in:** `README.md` line 98
- **Details:** Listed as a planned feature alongside RDP path simplification and elevation charts
- **Config/Code:** Not present in this repository

### GPS File Parsing
- **Status:** In development (TracePace v0.5.0-alpha)
- **Purpose:** Parse `.fit` (FIT) and `.gpx` (GPS Exchange) activity files
- **Details:** Custom Go binary parser for .fit files; GPX XML parsing also handled
- **Declared in:** `README.md` lines 90, 101

### RDP Path Simplification
- **Status:** In development (TracePace v0.5.0-alpha)
- **Purpose:** Ramer-Douglas-Peucker algorithm for clean vector traces on posters
- **Declared in:** `README.md` line 102

### Poster Export
- **Status:** In development (TracePace v0.5.0-alpha)
- **Purpose:** High-res PNG export with 3:4, 1:1, 16:9 aspect ratios
- **Details:** Multiple poster themes (World Marathon Majors + local races)
- **Declared in:** `README.md` lines 103-104

## Workflow Orchestration

### Temporal
- **Status:** Shipped (courtsite platform)
- **Purpose:** Booking workflows in Go + Temporal — checkout, rescheduling, cancellations, refunds
- **Declared in:** `README.md` line 76
- **Config/Code:** Not present in this repository

## IoT Integration

### Raspberry Pi
- **Status:** Shipped
- **Purpose:** Automated venue lighting based on booking schedules
- **Declared in:** `README.md` line 80
- **Config/Code:** Not present in this repository

## Infrastructure & DevOps

### GitHub Actions
- **Status:** In use
- **Purpose:** CI/CD pipelines
- **Declared in:** `README.md` line 56 (badge)
- **Config/Code:** Not present in this repository

### Cloudflare (General)
- **Status:** In use
- **Purpose:** CDN, DNS, DDoS protection
- **Declared in:** `README.md` line 57 (badge)
- **Config/Code:** Not present in this repository

## Environment Configuration

**Detected in this repository:**
- No `.env` files or environment configuration files present

**Inferred required env vars (from README declarations):**
- Payment gateway API keys (KiplePay, Spay Global)
- MyLHDN e-Invoice API credentials
- Cloudflare Turnstile site/secret keys
- JWT secret / OAuth client IDs
- Sentry DSN
- Database connection strings (PostgreSQL)
- Redis connection string
- Temporal server address
- Weather API key (for TracePace)

---

*Integration audit: 2026-05-25 — All integration information is self-reported via `README.md` badges and text. No SDK clients, API wrappers, configuration files, or credential files exist in this repository. Integrations are documented based on the developer's declared shipped work, primarily at courtsite and TracePace.*
