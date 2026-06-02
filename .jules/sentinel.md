## 2024-06-02 - [CRITICAL] Hardcoded Secret Bypass in XML-RPC configuration
**Vulnerability:** A hardcoded token `xrpc-9f8e7d6c5b4a` was present in the Nginx `wordpress.conf` configuration file, allowing anyone with the token to bypass the XML-RPC block and access the `/xmlrpc.php` endpoint.
**Learning:** Hardcoded secrets in infrastructure configuration files like Nginx can completely undermine application-level security and are often overlooked in standard code reviews.
**Prevention:** Always use unconditional blocks (`deny all;`) for disabled endpoints in Nginx. If authentication is necessary, use properly configured upstream mechanisms or securely managed environment variables, never plain-text tokens in source control.
