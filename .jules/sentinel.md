
## 2026-06-28 - [CRITICAL] Fix hardcoded secret bypass for XML-RPC
**Vulnerability:** A hardcoded token `xrpc-9f8e7d6c5b4a` was present in the Nginx reverse proxy configuration (`wordpress.conf`) to conditionally bypass a block on `/xmlrpc.php`. This violates the security rule against hardcoded secrets and provides a backdoor.
**Learning:** Checking query parameters like `$arg_token` for hardcoded secrets in Nginx configuration files is a security anti-pattern and can be exploited.
**Prevention:** Remove unconditional secret checks in proxy blocks and instead use robust authentication methods or unconditionally deny access to sensitive endpoints.
