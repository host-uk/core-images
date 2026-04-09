## 2026-02-17 - Hardcoded Secrets in Nginx Config
**Vulnerability:** Found a hardcoded XML-RPC token (`xrpc-9f8e7d6c5b4a`) in `server-php/config/conf.d/wordpress.conf` used to authorize access to `/xmlrpc.php`.
**Learning:** Nginx configurations are statically copied into the Docker image without `envsubst` or similar mechanisms, leading developers to hardcode secrets directly in the config file.
**Prevention:** Use unconditional blocks for sensitive endpoints like XML-RPC unless strictly necessary. If secrets are needed, implement a mechanism to inject them at runtime (e.g., `envsubst` in entrypoint) and never commit them to the repo.
