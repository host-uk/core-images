## 2024-05-15 - [CRITICAL] Nginx Hardcoded Secret in Configuration
**Vulnerability:** A hardcoded token (`$arg_token = "xrpc-9f8e7d6c5b4a"`) was used in `server-php/config/conf.d/wordpress.conf` to bypass the XML-RPC block, allowing anyone who discovers the config or knows the secret to bypass the intended block.
**Learning:** Hardcoded secrets in infrastructure configuration files (like Nginx) are just as dangerous as hardcoded secrets in application code, and can bypass intended application-level or routing-level security controls entirely.
**Prevention:** Nginx configuration files should rely on unconditional blocks, robust authentication schemes (like upstream checks or standard HTTP auth), or environment-injected configurations rather than hardcoded string matching.
