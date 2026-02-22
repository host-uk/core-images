## 2025-02-17 - Hardcoded Secrets in Nginx Config
**Vulnerability:** Found a hardcoded secret token (`xrpc-9f8e7d6c5b4a`) embedded directly in an Nginx configuration file (`wordpress.conf`) to bypass an XML-RPC block.
**Learning:** Secrets can hide in infrastructure configuration files (Nginx, HAProxy, etc.) as logic checks (e.g., `if ($arg_token = "...")`), not just in application code or `.env` files.
**Prevention:** Never hardcode secrets in Nginx logic. Use `deny all` by default for sensitive endpoints like `xmlrpc.php`. If access is needed, use upstream authentication or at least environment variables (though Nginx makes env vars hard without Lua/envsubst).
