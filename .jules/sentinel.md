## 2024-05-24 - [Nginx Hardcoded Secret in Query Parameter]
**Vulnerability:** A hardcoded secret token (`xrpc-9f8e7d6c5b4a`) was used to bypass an Nginx block for the `/xmlrpc.php` endpoint via an `$arg_token` check.
**Learning:** Checking query parameters (`$arg_`) for authentication in Nginx exposes secrets in access logs and is a bad security pattern.
**Prevention:** Unconditionally block potentially dangerous endpoints or implement proper upstream authentication. Never use hardcoded secrets in Nginx configuration files.