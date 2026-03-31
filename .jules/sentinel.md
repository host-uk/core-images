## 2025-02-18 - Hardcoded secret in Nginx config
**Vulnerability:** Found a hardcoded secret token (`xrpc-9f8e7d6c5b4a`) used to bypass the block on `/xmlrpc.php` in `server-php/config/conf.d/wordpress.conf`.
**Learning:** Hardcoded secrets in configuration files are easily exposed and cannot be rotated securely without a deployment. They provide a false sense of security and a persistent backdoor if leaked.
**Prevention:** Never use hardcoded secrets for authentication in server configurations. Instead, disable unnecessary endpoints completely (like `xmlrpc.php`), or implement proper authentication mechanisms (e.g., standard HTTP basic auth, API gateways, or upstream authentication).
