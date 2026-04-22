## 2024-05-16 - [Hardcoded Secret in Nginx XML-RPC Bypass]
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was left in `server-php/config/conf.d/wordpress.conf` allowing a bypass to the XML-RPC block, providing open access to a known vulnerable WordPress endpoint if the secret is discovered.
**Learning:** Hardcoded secrets in infrastructure configuration files (like Nginx) can bypass application-level security and are often missed by standard application secret scanners if not explicitly configured to check configuration files.
**Prevention:** Never hardcode secrets in configuration files. If an endpoint needs restriction, rely on standard mechanisms (like blocking outright if legacy, or proper upstream authentication) rather than hardcoded query parameter checks.
