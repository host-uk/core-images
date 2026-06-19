## 2024-06-19 - Hardcoded Secret in Nginx Config
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was used in `server-php/config/conf.d/wordpress.conf` to bypass the block on `/xmlrpc.php`.
**Learning:** Hardcoded secrets in infrastructure configuration files create significant security vulnerabilities. If this configuration is leaked or checked into version control, attackers can bypass security controls. Authentication logic should not rely on static tokens embedded in proxy configurations.
**Prevention:** Never use hardcoded tokens for access control in Nginx configurations. Endpoints like `xmlrpc.php` should be unconditionally blocked (`deny all;`) if they are not needed.
