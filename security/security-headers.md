# Security Headers Configuration

This document outlines the HTTP security headers enforced at the Azure Front Door
edge using the Rules Engine. All headers are applied globally and independently
of application-level configuration.

---

## Implemented Security Headers

### Strict-Transport-Security (HSTS)
Forces browsers to use HTTPS only and prevents protocol downgrade attacks.

---

### Content-Security-Policy (CSP)
Restricts content loading to trusted sources and mitigates cross-site scripting
(XSS) and injection attacks.

---

### X-Frame-Options
Prevents clickjacking by disallowing the site from being embedded in iframes.

---

### X-Content-Type-Options
Prevents browsers from MIME-type sniffing and executing unintended content types.

---

### Referrer-Policy
Limits the amount of referrer information shared during cross-origin requests.

---

### Permissions-Policy
Disables access to sensitive browser features unless explicitly required.

---

## Enforcement Location
- Azure Front Door Rules Engine
- Applied at the edge before traffic reaches the origin
- Ensures consistent security enforcement regardless of application logic

---

## Summary
Security headers are centrally enforced at the edge to improve consistency,
reduce application complexity, and provide baseline protection against common
web-based attacks.
