## 2024-03-01 - [Hardcoded Token in Nginx Config]
**Vulnerability:** A hardcoded XML-RPC bypass token (`xrpc-9f8e7d6c5b4a`) was found in `server-php/config/conf.d/wordpress.conf`.
**Learning:** Hardcoded secrets in Nginx configuration files (e.g., `$arg_token` checks) are strictly prohibited and must be replaced with unconditional blocks or proper upstream authentication mechanisms.
**Prevention:** Avoid embedding any sensitive credentials or tokens directly into configuration files. Use environment variables or rely on appropriate authentication mechanisms implemented in the application layer or dedicated authentication services.
