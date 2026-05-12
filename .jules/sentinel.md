## 2024-05-12 - [Hardcoded XML-RPC Bypass Token]
**Vulnerability:** A hardcoded token (`$arg_token = "xrpc-9f8e7d6c5b4a"`) was used in the Nginx configuration (`server-php/config/conf.d/wordpress.conf`) to bypass the block on `/xmlrpc.php`.
**Learning:** Hardcoded secrets in Nginx configuration files via `$arg_token` or similar variables create a static backdoor that is easily discoverable and exploitable.
**Prevention:** Remove unconditional bypasses based on static tokens. Use robust upstream authentication mechanisms or keep endpoints unconditionally blocked if not needed.
