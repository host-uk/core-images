## 2025-02-18 - Hardcoded Secret in Nginx Config
**Vulnerability:** Found a hardcoded secret token (`xrpc-9f8e7d6c5b4a`) in `server-php/config/conf.d/wordpress.conf` used to bypass XML-RPC block.
**Learning:** Hardcoded secrets in configuration files are critical vulnerabilities. Nginx configs are often overlooked for secrets.
**Prevention:** Use environment variables for secrets, or better yet, avoid bypass mechanisms based on static tokens. Always block XML-RPC unless strictly necessary.
