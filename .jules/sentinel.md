## 2026-06-07 - [CRITICAL] Fix Hardcoded Secret Bypass in XML-RPC configuration
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was left in the Nginx configuration `server-php/config/conf.d/wordpress.conf` which allowed bypassing the XML-RPC block (a common vector for brute force and amplification attacks).
**Learning:** Development or debugging backdoors using `if ($arg_token = "...")` in Nginx configuration files expose the system to unauthorized access if committed to production.
**Prevention:** Always unconditionally block access to sensitive files (like `xmlrpc.php`) with `deny all;` unless authenticated through proper, non-hardcoded mechanisms. Never commit secrets directly into source code or server configurations.
