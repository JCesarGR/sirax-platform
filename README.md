# SIRAX Platform

<p align="center">
  <img src="https://github.com/JCesarGR/sirax-platform/blob/main/download/sirax-hero.png" alt="SIRAX Platform Banner" width="100%" />
</p>

<p align="center">
  <strong>Identity Verification · Risk Intelligence · Digital Footprint Analysis · Compliance Screening</strong>
</p>

<p align="center">
  <em>Know More. Risk Less.</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Production%20Ready-00E5A8?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Platform-KYC%20%26%20Risk%20Intelligence-111827?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Focus-Mexico%20Verification-2563EB?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Built%20by-Synkdata%20Technologies-7C3AED?style=for-the-badge" />
</p>

---

## What is SIRAX?

**SIRAX** is an identity verification and risk intelligence platform designed to centralize multiple data sources into a single professional verification workflow.

The platform helps analyze identity data, validate official records, enrich digital footprints, identify risk indicators, and generate structured reports for compliance, due diligence, background verification, and operational risk analysis.

SIRAX was built with a modular provider architecture, allowing identity, OSINT, compliance, and enrichment modules to work together without breaking the main verification flow.

---

## Core Purpose

SIRAX answers a critical question:

> **How can an organization verify identity, detect risk, and understand digital exposure from one centralized platform?**

Instead of checking multiple providers manually, SIRAX organizes the process into one unified flow:

```txt
Input Data
   ↓
Identity Validation
   ↓
Digital Footprint Enrichment
   ↓
Risk & Compliance Screening
   ↓
Provider Normalization
   ↓
Structured Report
```

---

## Platform Preview

### Dashboard

<p align="center">
  <img src="./docs/assets/dashboard.png" alt="SIRAX Dashboard" width="100%" />
</p>

The dashboard centralizes the verification workflow, provider status, risk indicators, and subject analysis into a clean operational interface.

---

### Intelligence Modules

<p align="center">
  <img src="./docs/assets/modules.png" alt="SIRAX Intelligence Modules" width="100%" />
</p>

SIRAX is organized into independent modules that can be enabled, disabled, replaced, or expanded depending on the verification needs.

---

### Report Generation

<p align="center">
  <img src="./docs/assets/report.png" alt="SIRAX Report Generation" width="100%" />
</p>

The platform consolidates provider results into structured reports that can be used for review, documentation, and decision-making.

---

## Main Capabilities

### Identity Verification

SIRAX supports identity verification workflows focused on structured Mexican identity data.

Key capabilities include:

* CURP validation
* RFC validation
* Identity data normalization
* Provider-based verification
* Official data source integration
* Fallback provider support
* Validation status tracking

---

### Digital Footprint Intelligence

SIRAX includes a digital footprint module designed to enrich a subject profile using authorized, configured, and public data sources.

Supported analysis areas include:

* Email enrichment
* Phone enrichment
* Username discovery
* Public profile correlation
* Breach exposure indicators
* Search-based OSINT enrichment
* Multi-provider aggregation
* Digital exposure mapping

---

### Risk & Compliance Screening

The platform can organize and evaluate different risk signals from multiple sources.

Risk intelligence areas include:

* Sanctions indicators
* PEP-related indicators
* Public compliance list checks
* Open-source intelligence findings
* Provider evidence tracking
* Risk categorization
* Confidence scoring
* Final risk summary

---

### Provider Orchestration

SIRAX was designed to work with multiple external providers through a modular architecture.

Potential provider categories include:

* Identity providers
* Government validation providers
* OSINT providers
* Search intelligence providers
* Email enrichment providers
* Phone enrichment providers
* Compliance screening providers
* AI-assisted report providers

---

## Why SIRAX is Different

SIRAX is not just a form or a simple API wrapper.

It is designed as a complete verification workflow.

| Feature                   | Value                                                  |
| ------------------------- | ------------------------------------------------------ |
| Modular providers         | Add or replace providers without breaking the system   |
| Centralized workflow      | One place for identity, risk, OSINT, and reporting     |
| Provider status control   | Know which modules are active or missing configuration |
| Structured reports        | Turn raw provider data into useful intelligence        |
| Fallback logic            | Continue operating when a provider is unavailable      |
| Mexico-focused validation | Built around real identity verification needs          |
| Scalable architecture     | Ready to expand with new modules and providers         |

---

## Architecture

<p align="center">
  <img src="./docs/assets/architecture.png" alt="SIRAX Architecture" width="100%" />
</p>

```txt
SIRAX Platform
├── Identity Verification
│   ├── CURP
│   ├── RFC
│   ├── RENAPO
│   └── SAT
│
├── Digital Footprint Intelligence
│   ├── Email Enrichment
│   ├── Phone Enrichment
│   ├── Username Discovery
│   ├── Search Intelligence
│   └── OSINT Providers
│
├── Risk & Compliance
│   ├── Sanctions
│   ├── PEP Indicators
│   ├── Public Records
│   └── Risk Signals
│
├── Provider Registry
│   ├── Status Check
│   ├── Required ENV Vars
│   ├── Fallback Logic
│   └── Normalized Responses
│
└── Reporting Engine
    ├── Evidence Summary
    ├── Risk Summary
    ├── Provider Results
    └── Final Report
```

---

## Suggested Project Structure

```txt
src/
├── app/
├── components/
│   ├── dashboard/
│   ├── reports/
│   ├── forms/
│   └── ui/
├── lib/
│   ├── providers/
│   │   ├── identity/
│   │   ├── osint/
│   │   ├── compliance/
│   │   └── registry.ts
│   ├── services/
│   ├── validators/
│   └── utils/
├── public/
└── styles/
```

---

## Provider Registry

SIRAX uses a provider registry to centralize external integrations and safely check which services are enabled.

Each provider can define:

* Provider name
* Required environment variables
* Enabled or disabled status
* Request logic
* Error handling
* Timeout handling
* Normalized response structure
* Fallback behavior

Example:

```ts
export const provider = {
  name: "ProviderName",
  enabled: Boolean(process.env.PROVIDER_API_KEY),
  requiredEnv: ["PROVIDER_API_KEY"],
};
```

---

## System Status

SIRAX can expose a protected endpoint to verify provider configuration without exposing secrets.

```txt
GET /api/system/status
```

Example response:

```json
{
  "providers": {
    "serpapi": "enabled",
    "hunter": "enabled",
    "numverify": "missing_api_key",
    "apimarket": "enabled"
  }
}
```

---

## Environment Variables

Create a `.env` file based on `.env.example`.

```env
DATABASE_URL=
JWT_SECRET=

OPENAI_API_KEY=
GEMINI_API_KEY=

SERPAPI_API_KEY=
HIBP_API_KEY=
HUNTER_API_KEY=
NUMVERIFY_API_KEY=

NUBARIUM_API_KEY=
APIMARKET_API_KEY=

SMTP_HOST=
SMTP_PORT=
SMTP_USER=
SMTP_PASS=
```

Never commit real credentials to the repository.

---

## Installation

Clone the repository:

```bash
git clone https://github.com/JCesarGR/sirax-platform.git
cd sirax-platform
```

Install dependencies:

```bash
npm install
```

Run development server:

```bash
npm run dev
```

Build for production:

```bash
npm run build
```

Start production mode:

```bash
npm start
```

---

## Recommended Workflow

```bash
git checkout -b feature/new-module
npm run dev
npm run build
git add .
git commit -m "feat: add new module"
git push origin feature/new-module
```

---

## Security Guidelines

Before deploying or publishing this repository:

* Do not commit `.env` files
* Do not expose API keys
* Do not commit generated reports with real personal data
* Do not commit database dumps
* Do not expose raw provider responses publicly
* Validate and sanitize all external provider responses
* Use HTTPS in production
* Restrict admin routes
* Apply rate limits to public endpoints
* Rotate any key that was previously exposed

If a secret was ever committed, deleting it from the current code is not enough. The key must be rotated and the Git history should be cleaned before making the repository public.

---

## Compliance Notice

SIRAX is designed for authorized verification, compliance, and risk intelligence workflows.

The platform should only be used with lawful basis, user consent where required, and in accordance with applicable privacy, data protection, and compliance regulations.

This project does not encourage unauthorized surveillance, credential abuse, account intrusion, or misuse of third-party systems.

---

## Roadmap

* [ ] Provider health dashboard
* [ ] Advanced report builder
* [ ] Role-based access control
* [ ] Audit logs
* [ ] Risk scoring engine
* [ ] PDF report export
* [ ] Webhook support
* [ ] Multi-tenant support
* [ ] Admin analytics panel
* [ ] Additional fallback providers for CURP/RFC validation
* [ ] Expanded digital footprint intelligence module

---

## Brand

**SIRAX**
Identity & Risk Intelligence Platform

**Know More. Risk Less.**

Developed by **Synkdata Technologies**.

---

## Author

**Julio Cesar Rios Garcia**
Founder, Synkdata Technologies

GitHub: [@JCesarGR](https://github.com/JCesarGR)
Portfolio: [synkdata.online](https://synkdata.online)

---

## License

This project is proprietary software.

All rights reserved. Unauthorized copying, distribution, modification, or commercial use of this software is strictly prohibited without prior written permission.
