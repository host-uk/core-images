## 2024-05-18 - [CRITICAL] Hardcoded Token Bypass in Nginx Configuration
**Vulnerability:** A hardcoded token (`$arg_token = "xrpc-9f8e7d6c5b4a"`) was found in the Nginx configuration `server-php/config/conf.d/wordpress.conf`. It was intended to block `/xmlrpc.php` but acted as a backdoor, allowing anyone with the token to bypass the block.
**Learning:** Hardcoding secrets or bypass mechanisms inside web server configuration files (like Nginx `conf.d` files) can create critical hidden entry points or backdoors. These bypasses defeat the purpose of protective measures.
**Prevention:** Avoid putting hardcoded secrets or bypass tokens in configuration files. If an exception is absolutely necessary, use robust authentication mechanisms or IP whitelisting rather than static secret tokens.
