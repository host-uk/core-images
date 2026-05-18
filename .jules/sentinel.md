
## 2024-05-18 - [Fix hardcoded secret for XML-RPC bypass]
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was present in the Nginx configuration (`server-php/config/conf.d/wordpress.conf`) to bypass the XML-RPC block (`/xmlrpc.php`).
**Learning:** Hardcoding secrets or bypass tokens directly in configuration files exposes the application to unauthorized access if the configuration is leaked or accessible. Nginx logic is often used to implement these backdoors.
**Prevention:** Avoid using hardcoded tokens in configuration files. If an endpoint needs to be restricted, apply proper authentication mechanisms or unconditionally block access (`deny all;`) if it is not required by legitimate clients.
