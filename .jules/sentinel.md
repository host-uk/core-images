## 2024-05-22 - [CRITICAL] Fix hardcoded XML-RPC secret bypass

**Vulnerability:** A hardcoded token `xrpc-9f8e7d6c5b4a` was used in `server-php/config/conf.d/wordpress.conf` to conditionally bypass the `deny` rule for `xmlrpc.php`. This allows anyone with the token to access the XML-RPC endpoint.

**Learning:** Hardcoding secrets like bypass tokens in server configuration files makes them vulnerable to exposure through repository read access, config leaks, or accidental publishing. It overrides default security measures relying on environment variables or external authentication mechanisms.

**Prevention:** Never commit hardcoded secrets, passwords, or bypass tokens in configuration files. Use robust authentication methods (like OAuth, JWT) or restrict access based on secure, managed infrastructure like internal networks or VPNs, instead of simple shared secrets in Nginx configuration.
