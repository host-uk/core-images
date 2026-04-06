## 2024-05-27 - [Hardcoded xmlrpc Token]
**Vulnerability:** A hardcoded token `xrpc-9f8e7d6c5b4a` was found in `server-php/config/conf.d/wordpress.conf` to allow access to `/xmlrpc.php`.
**Learning:** Hardcoded secrets in Nginx configuration files can lead to security bypasses and should never be checked into version control.
**Prevention:** Hardcoded secrets in Nginx configuration files (e.g., `$arg_token` checks) are strictly prohibited and must be replaced with unconditional blocks or proper upstream authentication mechanisms.
