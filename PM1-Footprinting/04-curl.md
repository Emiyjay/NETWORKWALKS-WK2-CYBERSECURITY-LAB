# Curl Evidence Summary

Command: curl -I https://networkwalks.com

Observed:
- HTTP/2 200
- Server: Apache
- Content-Type: text/html; charset=UTF-8
- WordPress REST API references appeared in Link headers
- A __wpdm_client cookie was observed with Secure and HttpOnly attributes
- Referrer-Policy: no-referrer-when-downgrade
- X-Nginx-Cache: WordPress

The actual cookie value is intentionally omitted from this public repository.
