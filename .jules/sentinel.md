## 2024-06-26 - [CRITICAL] Fix hardcoded secret for XML-RPC bypass
**Vulnerability:** Found a hardcoded authentication bypass token (`xrpc-9f8e7d6c5b4a`) in `server-php/config/conf.d/wordpress.conf` that allows access to `/xmlrpc.php`, overriding the default block.
**Learning:** Hardcoding secrets directly in configuration files exposes the application to unauthorized access, especially when configuration files are version controlled or built directly into images. Nginx configuration should not be used as an authentication mechanism with hardcoded secrets.
**Prevention:** Unconditionally block sensitive endpoints like `/xmlrpc.php` in Nginx. If access is required, use proper authentication mechanisms or IP allowlisting instead of query parameter secrets.
