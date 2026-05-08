## 2026-05-08 - Fix hardcoded secret bypassing XML-RPC block
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was present in `server-php/config/conf.d/wordpress.conf` which allowed bypassing the XML-RPC access restrictions when appended as a query parameter (`?token=xrpc-9f8e7d6c5b4a`).
**Learning:** Hardcoded secrets in infrastructure configuration files (like Nginx) create permanent backdoors that defeat defense-in-depth mechanisms. Environmental substitution or proper upstream authentication should always be used.
**Prevention:** Never use hardcoded tokens for authorization logic in configuration files. Unconditionally block disallowed endpoints (`deny all;`) or use robust authentication proxies.
