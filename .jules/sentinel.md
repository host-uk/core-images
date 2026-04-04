## 2025-02-14 - Nginx XML-RPC Hardcoded Secret Bypass
**Vulnerability:** The Nginx configuration for WordPress (`server-php/config/conf.d/wordpress.conf`) contained a hardcoded secret token check (`$arg_token = "xrpc-9f8e7d6c5b4a"`) to bypass the `xmlrpc.php` block.
**Learning:** This architectural vulnerability pattern relies on Nginx-level bypasses using hardcoded `$arg_token` checks, effectively creating backdoors using hardcoded secrets in server configuration files instead of application code.
**Prevention:** Hardcoded secrets in Nginx configuration files are strictly prohibited. Always replace them with unconditional blocks (`deny all;`) or proper upstream authentication mechanisms. Disable logging for these unconditionally blocked endpoints to reduce log spam.
