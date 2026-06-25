
## 2024-06-25 - [Fix Critical] Remove Hardcoded Secret Bypass in XML-RPC
**Vulnerability:** A hardcoded authentication bypass was found in the Nginx configuration `server-php/config/conf.d/wordpress.conf` for the `/xmlrpc.php` endpoint. The configuration allowed access if the `$arg_token` matched a specific string (`xrpc-9f8e7d6c5b4a`).
**Learning:** Hardcoded secrets in configuration files are a critical risk because they provide an undocumented and easily discoverable mechanism to bypass security controls, especially when the codebase is accessible or inadvertently leaked.
**Prevention:** Unconditionally block access to sensitive endpoints like `/xmlrpc.php` using `deny all;` in Nginx configurations. If access is genuinely required, use proper external authentication mechanisms (like mutual TLS or dedicated auth upstream servers) instead of embedding secrets in static configuration logic.
