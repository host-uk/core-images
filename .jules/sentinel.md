# Sentinel Journal
## 2024-05-24 - [CRITICAL] Hardcoded Token in Nginx Configuration
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was found in `server-php/config/conf.d/wordpress.conf` allowing access to `/xmlrpc.php`.
**Learning:** Nginx configuration files were being used directly without environment variable substitution, leading to the hardcoding of secrets.
**Prevention:** Remove the hardcoded secret check and replace it with an unconditional `deny all;` block for `/xmlrpc.php`.
