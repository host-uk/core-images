## 2024-07-05 - [Hardcoded xmlrpc.php token in Nginx config]
**Vulnerability:** A hardcoded token `xrpc-9f8e7d6c5b4a` was used in `server-php/config/conf.d/wordpress.conf` to bypass the block on `/xmlrpc.php`.
**Learning:** Hardcoded secrets in infrastructure configuration provide a false sense of security and can easily leak via source control, granting permanent unauthorized access.
**Prevention:** Instead of using hardcoded secrets in Nginx for application functionality, use robust upstream authentication, or simply block high-risk obsolete endpoints like `/xmlrpc.php` completely.
