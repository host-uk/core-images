## 2025-05-05 - [CRITICAL] Fix Hardcoded Nginx Bypass Token for XML-RPC

**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was present in `server-php/config/conf.d/wordpress.conf` allowing a bypass to the default block on `/xmlrpc.php`. This hardcoded secret could be discovered by anyone with read access to the source code, allowing unauthorized access to the XML-RPC endpoint, which is commonly targeted for brute-force and DDoS attacks against WordPress.

**Learning:** Hardcoded tokens or passwords directly in Nginx configurations bypass standard authentication mechanisms and violate the principle of not storing secrets in source control. The token mechanism was likely intended to provide a specific service or administrator access but failed to use secure secret management.

**Prevention:** Never hardcode secrets in Nginx configuration files (e.g., checking `$arg_token`). Endpoints like XML-RPC should be completely disabled (`deny all;`) if unused, or secured using appropriate upstream authentication that relies on proper secret management or standard HTTP Basic Auth, rather than URL query parameters.
