## 2026-04-11 - Hardcoded Secret in Nginx Config
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was found in `server-php/config/conf.d/wordpress.conf` to conditionally allow access to the otherwise blocked `/xmlrpc.php` endpoint.
**Learning:** Nginx configuration files in this environment are used directly without environment variable substitution (via `envsubst`). Therefore, trying to use environment variables for secrets in Nginx configuration leads to hardcoded strings that can be exposed.
**Prevention:** Strictly prohibit hardcoded secrets in Nginx configuration files. Implement unconditional blocks or use proper upstream authentication mechanisms instead of hardcoded conditional checks.
