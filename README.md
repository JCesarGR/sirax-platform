# SIRAX

### Identity & Risk Intelligence Platform

**Know More. Risk Less.**

SIRAX is a modular identity verification, digital footprint intelligence, and risk analysis platform designed to centralize multiple verification sources into a single structured workflow.

The platform helps organizations validate identities, enrich subject profiles, detect risk indicators, and generate consolidated reports for compliance, due diligence, and background verification processes.

---

## Overview

SIRAX was built as a verification and intelligence platform focused on the Mexican market, with a scalable architecture that allows external providers, OSINT modules, compliance sources, and identity validation services to work together without breaking the main verification flow.

The system is designed to support:

* Identity verification
* CURP and RFC validation
* Digital footprint enrichment
* Risk indicator detection
* Compliance and sanctions screening
* Provider fallback logic
* Automated report generation
* Admin and operational workflows

---

## Key Features

### Identity Verification

SIRAX includes identity validation modules that help verify and normalize personal information through structured checks.

Supported workflows may include:

* CURP validation
* RFC validation
* RENAPO provider integration
* SAT provider integration
* Identity data normalization
* Validation status tracking
* Provider fallback support

---

### Digital Footprint Intelligence

The digital footprint module enriches a subject profile using authorized, public, and configured data providers.

Supported intelligence areas include:

* Email enrichment
* Phone enrichment
* Username discovery
* Public profile correlation
* Breach exposure indicators
* Social presence detection
* Search-based OSINT enrichment
* Multi-provider data aggregation

Optional or planned integrations may include:

* HaveIBeenPwned
* Hunter.io
* NumVerify
* SerpAPI
* Sherlock
* Maigret
* Maltego-compatible workflows

---

### Risk & Compliance Screening

SIRAX can consolidate risk signals from different sources and organize them into a structured risk profile.

Risk and compliance areas may include:

* Sanctions screening
* PEP indicators
* Public compliance lists
* Open-source intelligence findings
* Source-based evidence tracking
* Risk categorization
* Confidence scoring
* Final risk summary

---

### Automated Reports

SIRAX is designed to generate structured reports that consolidate all verification results into a clear and professional format.

Reports may include:

* Identity validation results
* Provider response summaries
* Digital footprint findings
* Risk indicators
* Evidence references
* Confidence levels
* Final assessment
* Recommended next actions

---

## Architecture

SIRAX follows a modular provider-based architecture. Each external source is handled as an independent provider, allowing the platform to add, disable, or replace integrations without affecting the core workflow.

```txt
src/
├── app/
├── components/
├── lib/
│   ├── providers/
│   │   ├── identity/
│   │   ├── osint/
│   │   ├── compliance/
│   │   └── registry.ts
│   ├── services/
│   ├── utils/
│   └── validators/
├── public/
└── styles/
```

---

## Provider System

The provider system allows SIRAX to centralize external integrations and expose their status without revealing sensitive credentials.

Each provider can define:

* Provider name
* Required environment variables
* Enabled or disabled status
* Request logic
* Timeout handling
* Error handling
* Normalized response format
* Fallback behavior when applicable

Example provider structure:

```ts
export const provider = {
  name: "ProviderName",
  enabled: Boolean(process.env.PROVIDER_API_KEY),
  requiredEnv: ["PROVIDER_API_KEY"],
};
```

---

## System Status

SIRAX may expose a protected system status endpoint to verify which providers are correctly configured.

Example:

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

This endpoint should never expose real API keys, secrets, tokens, or credentials.

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
git clone https://github.com/Snupdrack/plataformasirax.git
cd plataformasirax
```

Install dependencies:

```bash
npm install
```

Run the development server:

```bash
npm run dev
```

Build for production:

```bash
npm run build
```

Start in production mode:

```bash
npm start
```

---

## Recommended Development Workflow

Create a new branch before making changes:

```bash
git checkout -b feature/new-module
```

Run the project locally:

```bash
npm run dev
```

Check the project before committing:

```bash
npm run build
```

Commit changes:

```bash
git add .
git commit -m "feat: add new provider module"
```

Push the branch:

```bash
git push origin feature/new-module
```

---

## Security Guidelines

Before deploying or publishing this repository:

* Remove all `.env` files
* Rotate any exposed API keys
* Remove test credentials
* Avoid committing personal data
* Avoid committing generated reports
* Avoid committing database dumps
* Validate all external provider responses
* Avoid exposing raw provider responses publicly
* Log errors without exposing sensitive data
* Apply rate limits to public endpoints
* Restrict admin routes
* Use HTTPS in production

If any secret was previously committed, deleting it from the current code is not enough. The key must be rotated in the provider dashboard and the Git history should be cleaned before making the repository public.

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

## Tech Stack

SIRAX may use technologies such as:

* React / Next.js
* Node.js
* TypeScript
* API routes
* External verification providers
* OSINT enrichment modules
* Database integration
* SMTP notifications
* Docker-ready deployment
* Cloud or VPS infrastructure

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
