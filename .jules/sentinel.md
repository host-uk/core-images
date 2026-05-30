## 2024-05-15 - [Remove hardcoded XML-RPC secret token]
**Vulnerability:** A hardcoded secret token (`xrpc-9f8e7d6c5b4a`) was found in `server-php/config/conf.d/wordpress.conf` to conditionally allow access to `/xmlrpc.php`.
**Learning:** Hardcoded secrets in infrastructure configuration (like Nginx config) can be leaked through source code access, making the "secret" bypass trivial to discover and exploit for anyone with access to the repo. It's a critical risk.
**Prevention:** Avoid using hardcoded secrets in Nginx config files (`$arg_token` checks) to gate endpoints. Instead, use unconditional blocks (`deny all;`) or secure, dynamic authentication mechanisms (e.g., standard Auth Request module).
