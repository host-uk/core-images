## 2026-06-15 - Remove Hardcoded XML-RPC Token
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was present in `server-php/config/conf.d/wordpress.conf` allowing unauthorized access to the `/xmlrpc.php` endpoint.
**Learning:** Hardcoding secrets or bypass tokens in Nginx configuration files creates a critical security vulnerability that can be exploited by anyone who discovers the token, especially since it is checked unconditionally.
**Prevention:** Remove hardcoded tokens from configuration files. Access to sensitive endpoints should be controlled via secure, properly authenticated mechanisms, or blocked entirely by returning 403 or 444 if the endpoint is not needed.
