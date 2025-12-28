# Azure Static Website + Front Door (GreenITSec)

## Overview
This project demonstrates a production-grade Azure static website hosted on Azure Storage and delivered securely through Azure Front Door. The lab focuses on secure edge delivery, DNS configuration, HTTPS enforcement, and security hardening rather than just hosting static content.

The site is accessible via a custom domain and is designed to reflect real-world enterprise patterns for performance, security, and reliability.

---

## Architecture
**Core components:**
- Azure Storage Account (Static Website)
- Azure Front Door (Standard/Premium)
- Azure DNS (custom domain)
- Front Door managed TLS certificates
- Rules Engine for redirects and security headers

**Traffic flow:**
User → Azure Front Door → Azure Storage Static Website

---

## Skills Demonstrated
- Azure DNS zone configuration and TXT validation
- Azure Front Door origin groups, routes, and rulesets
- HTTPS enforcement and HTTP → HTTPS redirects
- Blocking direct access to Front Door default domains
- Edge-based security header enforcement
- Troubleshooting DNS, TLS, and Front Door propagation issues

---

## Security Hardening
Security controls implemented at the Front Door edge:

- HTTPS enforced with automatic redirects
- Default `*.azurefd.net` endpoint blocked
- HTTP Strict Transport Security (HSTS)
- Content Security Policy (CSP)
- X-Frame-Options
- X-Content-Type-Options
- Referrer-Policy
- Permissions-Policy

All headers are applied using Front Door Rules Engine rather than application-level configuration.

---

## Validation & Testing
- Verified HTTPS enforcement using browser and curl
- Confirmed security headers via response inspection
- Validated DNS records and Front Door domain approval
- Tested direct access blocking to Front Door default hostname

---

## Observability & Performance
- Azure Front Door provides global edge caching and acceleration
- Azure Monitor and diagnostics can be enabled for traffic analysis and logging
- Low-latency global access without application servers

---

## Cost Estimate
Approximate monthly cost:
- Azure Storage Static Website: ~$0.50
- Azure Front Door (light traffic): ~$1.00–$2.50

Total: **~$1.50–$3.00/month**

---

## Project Structure

The repository is organized to separate application content, infrastructure configuration, security controls, and deployment documentation.

```text
.
├── site/
│   ├── index.html          # Main static website entry point
│   ├── styles.css          # Site styling
│   └── assets/             # Images, icons, and static resources
│
├── infrastructure/
│   ├── architecture-diagram.png   # High-level Azure architecture diagram
│   └── dns-records.md              # DNS records used for custom domain validation
│
├── security/
│   ├── frontdoor-rules.md          # Azure Front Door ruleset configuration
│   ├── security-headers.md         # Implemented HTTP security headers
│   └── https-enforcement.md        # HTTPS redirect and enforcement logic
│
├── observability/
│   ├── monitoring.md               # Azure Monitor and diagnostics configuration
│   └── logging.md                  # Traffic and access logging strategy
│
├── deployment/
│   ├── azure-cli-commands.md       # Azure CLI commands used for setup
│   └── validation-tests.md         # curl and browser-based validation tests
│
└── README.md


---

## Future Improvements
- Add Web Application Firewall (WAF) policy
- Enable Azure Monitor alerts and diagnostic logs
- Automate deployment with GitHub Actions
- Rebuild infrastructure using Bicep or Terraform
- Add availability and performance testing

---

## Why This Lab Matters
This project demonstrates practical Azure cloud engineering skills:
- Secure edge delivery
- DNS and TLS troubleshooting
- Infrastructure documentation
- Production-minded design decisions

It reflects patterns commonly used in enterprise environments and aligns with Azure, security, and identity-focused roles.

---

## Author
**Kerenton Green**  
GreenITSec  
