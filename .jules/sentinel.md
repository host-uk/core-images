## 2024-07-04 - [Hardcoded Nginx Secret Bypass]
**Vulnerability:** A hardcoded secret token (`xrpc-9f8e7d6c5b4a`) was found in Nginx configuration `server-php/config/conf.d/wordpress.conf` to bypass the block on `/xmlrpc.php`.
**Learning:** Hardcoded secrets in Nginx configurations can be exposed and compromised. Upstream authentication mechanisms should be used instead.
**Prevention:** Never use `$arg_` checks with hardcoded strings for access control. Always block sensitive endpoints unconditionally or rely on robust authentication systems.
