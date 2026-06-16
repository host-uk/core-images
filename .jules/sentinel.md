
## 2024-06-16 - [Hardcoded Authentication Secret in Nginx Config]
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was found in the Nginx configuration (`server-php/config/conf.d/wordpress.conf`) to bypass the block on `/xmlrpc.php` via `$arg_token`.
**Learning:** Checking query parameters like `$arg_token` for hardcoded static secrets directly in Nginx configuration files exposes sensitive access mechanisms, as configuration files are often tracked in version control.
**Prevention:** Avoid embedding hardcoded secrets directly into Nginx configurations. If an endpoint like XML-RPC must be blocked, do it unconditionally (`deny all;`). For authenticated bypasses, rely on proper upstream authentication mechanisms instead of Nginx variable checks.
