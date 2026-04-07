
## 2024-05-24 - [Fix hardcoded XML-RPC secret bypass]
**Vulnerability:** A hardcoded secret token (`xrpc-9f8e7d6c5b4a`) was found in the Nginx configuration (`server-php/config/conf.d/wordpress.conf`) allowing bypass of the XML-RPC endpoint block (`/xmlrpc.php`). This is a critical security risk as hardcoded secrets in version control can be discovered and exploited by attackers.
**Learning:** Hardcoded secrets, even if intended for internal use or as "tokens", present a major security vulnerability when committed to source control. They create backdoors that bypass intended access controls.
**Prevention:** Never use hardcoded secrets for authentication or access control in configuration files or code. Use environment variables or robust, managed authentication mechanisms instead. Unconditionally block endpoints like XML-RPC if they are not strictly required, and disable logging to prevent log pollution.
