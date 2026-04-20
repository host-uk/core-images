## 2026-04-20 - [Hardcoded Secret in Nginx Config]
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was found in `server-php/config/conf.d/wordpress.conf` to conditionally allow access to `xmlrpc.php`, completely bypassing the intended security block for anyone who discovers the token.
**Learning:** Hardcoded authentication tokens embedded directly within Nginx configuration files create severe, easily exploitable backdoors and defeat the purpose of endpoint restrictions.
**Prevention:** Unconditionally block sensitive endpoints (like `xmlrpc.php`) or use robust authentication mechanisms (e.g., proper upstream authorization, mutually authenticated TLS). Never use hardcoded query parameters for security bypasses.
