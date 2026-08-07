# 07 — Security Architecture (v0.1, reorganized)

## Layers

Cloudflare edge → Ubuntu firewall → Reverse proxy → Application security

## Controls

- MFA support, OAuth
- CSRF / XSS / SQL injection protection
- Parameterized queries
- Secure headers
- CAPTCHA
- Rate limits
- DDoS monitoring
- Audit logs
- Threat feeds
- Backups, disaster recovery

## Build Note

This should be implemented as shared middleware from the first commit
(see 09 — Development Standards) rather than retrofitted per-service.
