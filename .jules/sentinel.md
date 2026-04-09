## 2026-02-23 - Hardcoded XML-RPC Secret
**Vulnerability:** A hardcoded secret token (`xrpc-9f8e7d6c5b4a`) was found in `server-php/config/conf.d/wordpress.conf` allowing bypass of the XML-RPC block.
**Learning:** Hardcoding secrets in configuration files, even for "internal" bypasses, is a critical security risk as the code is visible to anyone with repository access.
**Prevention:** Use environment variables for secrets, or better yet, disable insecure features like XML-RPC entirely if they are not needed. If access is required, use proper authentication mechanisms.
