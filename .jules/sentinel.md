## 2024-05-25 - [Fix hardcoded token bypass for XML-RPC]
**Vulnerability:** A hardcoded token `xrpc-9f8e7d6c5b4a` was used to bypass the default block on `/xmlrpc.php` in Nginx configuration. This allows anyone with the token to access the potentially vulnerable XML-RPC endpoint.
**Learning:** Hardcoding secrets (like `$arg_token` checks) in Nginx configurations provides a false sense of security and exposes endpoints if the configuration or the secret is leaked.
**Prevention:** Unconditionally block known-vulnerable endpoints (like `/xmlrpc.php`) or use proper authentication mechanisms like basic auth or an upstream authentication provider instead of hardcoded URL parameters.
