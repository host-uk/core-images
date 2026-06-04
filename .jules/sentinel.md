
## 2024-06-04 - [CRITICAL] Fix hardcoded secret in Nginx configuration
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was present in `/app/server-php/config/conf.d/wordpress.conf` to bypass the XML-RPC block (`/xmlrpc.php`). This could allow attackers to bypass access controls if the configuration file is leaked or the token is discovered.
**Learning:** Hardcoding secrets directly in server configurations (like Nginx) poses a significant risk as these files are often tracked in version control and may be exposed. The `xmlrpc.php` endpoint in WordPress is a common vector for brute-force and DDoS attacks.
**Prevention:** Remove hardcoded secrets from configuration files. If an endpoint is unnecessary, block it unconditionally. If authentication is required, use proper authentication mechanisms like environment variables injected at runtime, or basic auth, rather than static tokens checked in Nginx logic.
