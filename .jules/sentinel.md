## 2024-05-24 - [Hardcoded secret in Nginx configuration]
**Vulnerability:** A hardcoded token `xrpc-9f8e7d6c5b4a` was found in `server-php/config/conf.d/wordpress.conf` to bypass the XML-RPC block.
**Learning:** Hardcoded secrets in Nginx configuration files are strictly prohibited as per memory.
**Prevention:** Always use proper authentication or unconditionally block such endpoints if they are not needed.
