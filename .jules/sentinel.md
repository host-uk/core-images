
## 2026-06-23 - [Fix hardcoded secret in Nginx configuration]
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was found in the `wordpress.conf` Nginx configuration file, allowing bypass of the XML-RPC block (`/xmlrpc.php?token=xrpc-9f8e7d6c5b4a`).
**Learning:** Hardcoded secrets in Nginx configuration files present a critical security vulnerability as they allow unauthorized access or bypasses and are difficult to rotate. In this case, it permitted access to XML-RPC, a feature often targeted by attackers for amplification and brute-force attacks.
**Prevention:** Unconditionally block sensitive endpoints if they are not needed, or use proper upstream authentication mechanisms instead of hardcoded secrets in configuration files.
