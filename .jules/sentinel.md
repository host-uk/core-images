## 2024-04-27 - [Hardcoded Secret in Nginx Config]
**Vulnerability:** A hardcoded token `xrpc-9f8e7d6c5b4a` was discovered in `server-php/config/conf.d/wordpress.conf` to allow bypass of the `/xmlrpc.php` restriction.
**Learning:** Hardcoding bypass tokens in Nginx configuration files is dangerous as the secret is checked into source control and visible to everyone.
**Prevention:** Never use `$arg_token = "secret"` checks in Nginx configuration. Completely block vulnerable endpoints (like `/xmlrpc.php`) or implement a robust authentication strategy instead.
