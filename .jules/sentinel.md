## 2025-05-27 - Hardcoded XML-RPC Token
**Vulnerability:** A hardcoded token `xrpc-9f8e7d6c5b4a` was found in `server-php/config/conf.d/wordpress.conf` used to gate access to `xmlrpc.php`.
**Learning:** Developers likely intended this as a placeholder or a quick way to secure XML-RPC without fully disabling it, but committed the secret to the repository.
**Prevention:** Use environment variables for secrets, or disable risky features like XML-RPC by default if they are not needed. Never commit secrets to version control.
