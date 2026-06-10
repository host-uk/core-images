## 2026-06-10 - [CRITICAL] Fix hardcoded secret for XML-RPC bypass
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) in `server-php/config/conf.d/wordpress.conf` was used to conditionally bypass the XML-RPC block (`/xmlrpc.php`), creating a backdoor that an attacker could easily discover and exploit.
**Learning:** Hardcoded secrets in Nginx configuration files create permanent backdoors. Nginx's `$arg_token` mechanism is insecure when tied to static strings committed to source control.
**Prevention:** Remove hardcoded conditional blocks for authentication. Block risky endpoints unconditionally (`deny all;`). If authentication is needed, use proper upstream authentication or environment variable substitution at runtime instead of hardcoding secrets in configuration files.
