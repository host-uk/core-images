## 2024-05-18 - [CRITICAL] Fix hardcoded secret bypass in XML-RPC
**Vulnerability:** Found a hardcoded token check (`if ($arg_token = "xrpc-9f8e7d6c5b4a")`) in the Nginx configuration for `/xmlrpc.php`, which allowed attackers to bypass security restrictions and access the endpoint unconditionally if they provided this token.
**Learning:** Hardcoded secrets in Nginx configuration files, such as `$arg_token` checks to bypass an intended restriction, act as backdoors and are a critical vulnerability.
**Prevention:** Always unconditionally block sensitive endpoints like `/xmlrpc.php` if not in use, or use a proper upstream authentication mechanism rather than embedding secrets in the configuration files directly.
