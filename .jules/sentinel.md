## 2024-05-15 - [CRITICAL] Fix hardcoded XML-RPC secret bypass
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was present in `server-php/config/conf.d/wordpress.conf` allowing a bypass to the default block on `/xmlrpc.php`.
**Learning:** Hardcoding secrets directly in Nginx configurations allows anyone with access to the source code to bypass intended security controls. Secrets should not be embedded in `.conf` files.
**Prevention:** Never use static strings to bypass security controls in Nginx configurations. Instead, rely on proper authentication mechanisms, block vulnerable endpoints unconditionally when possible, or inject necessary tokens through secure environment variables at runtime if an exception is truly needed.
