## 2024-04-08 - [CRITICAL] Hardcoded Secret Bypass in Nginx Configuration
**Vulnerability:** A hardcoded secret token (`xrpc-9f8e7d6c5b4a`) was found in the Nginx configuration (`server-php/config/conf.d/wordpress.conf`) to bypass the XML-RPC block via the `$arg_token` check.
**Learning:** Checking query string arguments directly in Nginx configuration files with hardcoded values is an insecure pattern found in this codebase. Nginx configurations are often public or easily exposed, leading to secret leaks and unauthorized access bypass.
**Prevention:** Hardcoded secrets in Nginx configuration files must be strictly prohibited. Endpoints like XML-RPC should be unconditionally blocked or proper upstream authentication mechanisms should be used.
