## 2024-05-15 - [CRITICAL] Fix hardcoded secret bypass in XML-RPC
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was present in the Nginx configuration for WordPress (`wordpress.conf`), allowing a bypass to access the `/xmlrpc.php` endpoint which is otherwise blocked.
**Learning:** Hardcoding secrets directly into configuration files or application logic is a critical security risk. It bypasses proper authentication mechanisms and provides a backdoor that is trivial to exploit if the configuration is exposed.
**Prevention:** Unconditionally block sensitive or deprecated endpoints like `/xmlrpc.php` in Nginx. If access is genuinely required, use robust upstream authentication mechanisms rather than simple query parameter tokens.
