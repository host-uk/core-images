## 2024-05-31 - [CRITICAL] Fix hardcoded secret bypass in Nginx config
**Vulnerability:** A hardcoded token `xrpc-9f8e7d6c5b4a` was discovered in `server-php/config/conf.d/wordpress.conf` allowing a bypass to the blocked `/xmlrpc.php` endpoint.
**Learning:** Hardcoding secrets directly into source code, specifically in configuration files such as Nginx config files, constitutes a major vulnerability, as they could be easily compromised.
**Prevention:** Unconditional blocks (`deny all;`) should be utilized for endpoints that are blocked for security purposes. No secrets should be hardcoded within configuration files. Ensure that configuration changes are reviewed strictly for such embedded tokens.
