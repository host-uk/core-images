## 2024-05-24 - [Nginx Hardcoded Secret]
**Vulnerability:** A hardcoded token bypass (`$arg_token = "xrpc-9f8e7d6c5b4a"`) was found in `server-php/config/conf.d/wordpress.conf` allowing access to `/xmlrpc.php`.
**Learning:** Hardcoded secrets in Nginx configuration files can be easily leaked or discovered, providing unauthorized access to restricted endpoints.
**Prevention:** Remove hardcoded secrets from configuration files. Use secure, environment-based authentication or restrict access entirely if the endpoint is not needed (e.g., using `deny all;`).
