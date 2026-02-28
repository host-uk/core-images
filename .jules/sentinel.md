## 2026-02-28 - [Nginx Configuration Hardcoded Secret & XML-RPC Bypass]
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was found in the `server-php/config/conf.d/wordpress.conf` Nginx configuration file. It was used as a bypass (`?token=xrpc-9f8e7d6c5b4a`) to access the `xmlrpc.php` endpoint, which was otherwise blocked. This posed a significant risk as the token was committed to version control and exposed the XML-RPC endpoint, which is known for brute-force and amplification attack risks.
**Learning:** Hardcoded secrets in infrastructure configuration files (like Nginx) are a critical vulnerability, especially when they expose dangerous endpoints. The XML-RPC endpoint should not have any bypass mechanisms in modern WordPress installations unless explicitly required and secured via proper upstream authentication.
**Prevention:**
1. Never commit secrets to configuration files.
2. Unconditionally block known dangerous endpoints like `/xmlrpc.php` in Nginx (`deny all;`).
3. If access is needed, rely on proper authentication mechanisms rather than custom query parameter tokens.
