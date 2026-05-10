
## 2025-05-10 - [CRITICAL] XML-RPC Hardcoded Secret Bypass in Nginx Configuration
**Vulnerability:** The Nginx configuration for WordPress (`server-php/config/conf.d/wordpress.conf`) contained a hardcoded secret token (`xrpc-9f8e7d6c5b4a`) that bypassed the default restriction on the `/xmlrpc.php` endpoint.
**Learning:** Hardcoding secrets or bypass tokens in web server configurations (like Nginx `if` statements checking `$arg_token`) creates a static backdoor. It defeats the purpose of disabling vulnerable endpoints and could be easily discovered by attackers analyzing source code or observing URL patterns.
**Prevention:** Remove unconditional endpoints that should be disabled entirely instead of providing hidden "secret" bypasses. If conditional access is required, implement properly authenticated mechanisms or IP whitelisting rather than static query parameter tokens in configuration files.
