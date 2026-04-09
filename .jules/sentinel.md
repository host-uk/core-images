## 2026-02-20 - Hardcoded Secret in Nginx Config
**Vulnerability:** Found a hardcoded secret token (`xrpc-9f8e7d6c5b4a`) in `server-php/config/conf.d/wordpress.conf` used to bypass XML-RPC blocking.
**Learning:** Hardcoded secrets in configuration files are easily overlooked, especially when used for "convenience" bypasses. They persist in the image and can be exploited if the image is used publicly.
**Prevention:** Use environment variables for all secrets. For XML-RPC, it's safer to block it entirely unless specifically needed, in which case a proper authentication mechanism (not a simple query param check) should be used, or the secret should be injected at runtime.
