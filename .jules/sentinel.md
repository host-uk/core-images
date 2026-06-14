
## 2024-05-27 - [CRITICAL] Fix hardcoded secret in XML-RPC bypass
**Vulnerability:** A hardcoded secret token (`xrpc-9f8e7d6c5b4a`) was present in `server-php/config/conf.d/wordpress.conf` to conditionally allow access to the `/xmlrpc.php` endpoint. This could allow attackers who discover the token to exploit WordPress XML-RPC vulnerabilities (e.g., brute-force attacks, pingback attacks).
**Learning:** Hardcoded secrets in Nginx configuration files provide a false sense of security and are easily discovered if the repository is accessible. Security should not rely on obscurity.
**Prevention:** Unconditionally block sensitive endpoints like `/xmlrpc.php` in Nginx configuration using `deny all`. If access is required, use robust authentication mechanisms instead of hardcoded tokens in the configuration file.
