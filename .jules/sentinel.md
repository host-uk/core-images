## 2024-05-14 - [XML-RPC Hardcoded Secret Bypass]
**Vulnerability:** A hardcoded secret (`xrpc-9f8e7d6c5b4a`) in `server-php/config/conf.d/wordpress.conf` was being used to bypass the XML-RPC block via the `?token=` parameter.
**Learning:** Hardcoded secrets in Nginx configuration files can lead to security bypasses if discovered, as they provide a permanent backdoor that cannot be easily rotated.
**Prevention:** Always use unconditional blocks (`deny all;`) for dangerous endpoints, or implement proper upstream authentication without relying on hardcoded parameter checks in web server configs.