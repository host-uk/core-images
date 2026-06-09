
## 2024-06-09 - [CRITICAL] Hardcoded Authentication Bypass in Nginx Config
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was present in `server-php/config/conf.d/wordpress.conf` allowing a complete bypass of the `deny all` security control for XML-RPC (`/xmlrpc.php`). Attackers with knowledge of the configuration or through brute-forcing could use this token to access XML-RPC and launch pingback amplification attacks or brute-force user credentials.
**Learning:** Hardcoding secrets directly into configuration files to provide temporary or conditional bypasses creates severe, persistent vulnerabilities that may easily leak through source control or server misconfigurations.
**Prevention:** Never use hardcoded tokens for authorization or authentication in web server configurations. Rely on robust authentication mechanisms, proper API gateways, and block risky endpoints unconditionally if they are not required.
