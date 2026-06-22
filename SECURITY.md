# Security Policy

## SIRAX Platform Security

SIRAX is an identity verification and risk intelligence platform designed for authorized KYC, compliance, digital footprint analysis, OSINT enrichment, and risk scoring workflows.

Because this project may interact with sensitive identity data, provider integrations, API credentials, reports, and compliance-related information, security reports must be handled responsibly.

---

## Reporting a Vulnerability

Please do not report security vulnerabilities through public GitHub Issues.

If you discover a vulnerability, exposed credential, authentication issue, data exposure risk, access control problem, or any security concern related to this project, please report it privately.

Contact:

**Synkdata Technologies**
**[contacto@sirax.lat](mailto:contacto@sirax.lat)**


When reporting, please include:

* A clear description of the vulnerability
* Steps to reproduce the issue
* Impact assessment
* Affected files, routes, endpoints, or modules
* Screenshots or logs if available
* Suggested mitigation, if known

Please avoid including real personal data, credentials, private keys, tokens, or sensitive third-party data in the report.

---

## Responsible Disclosure

We ask security researchers, contributors, and users to follow responsible disclosure practices.

Please allow reasonable time for review, validation, patching, and deployment before making any vulnerability details public.

Do not use security findings to:

* Access unauthorized accounts
* Extract personal data
* Exfiltrate provider responses
* Abuse API endpoints
* Bypass authentication
* Perform credential attacks
* Disrupt service availability
* Publish sensitive information

---

## Supported Security Areas

Security reports may include, but are not limited to:

* Authentication vulnerabilities
* Authorization bypass
* Exposed API keys or secrets
* Insecure environment variable handling
* Sensitive data exposure
* Injection vulnerabilities
* Broken access control
* Improper provider response handling
* Report generation leaks
* Misconfigured admin routes
* Insecure file uploads
* Rate limit bypass
* Logging of sensitive information

---

## Sensitive Data Guidelines

Do not commit or publish:

* `.env` files
* API keys
* JWT secrets
* SMTP credentials
* Database URLs
* Provider tokens
* Real CURP, RFC, phone, email, or identity data
* Generated reports containing personal information
* Database dumps
* Raw third-party provider responses with sensitive information

If a secret was exposed, deleting it from the repository is not enough. The credential must be rotated immediately and the Git history should be reviewed.

---

## Security Recommendations

Before deploying SIRAX in production:

* Use HTTPS
* Restrict admin routes
* Apply rate limits
* Validate and sanitize all inputs
* Sanitize provider responses
* Protect report downloads
* Use strong JWT secrets
* Store secrets only in environment variables
* Monitor provider errors and suspicious activity
* Disable unused providers
* Keep dependencies updated
* Review logs for sensitive data exposure
* Apply role-based access control where needed

---

## Responsible Use

SIRAX must only be used for lawful, authorized, and legitimate verification workflows.

This project does not support unauthorized surveillance, credential abuse, account intrusion, harassment, data scraping against terms of service, or misuse of identity intelligence tools.

Users are responsible for complying with applicable privacy, data protection, compliance, and cybersecurity laws.

---

## Status

Current security contact:

**[contacto@sirax.lat](mailto:contacto@sirax.lat)**

Security policy maintained by:

**Synkdata Technologies**
