## 2025-05-08 - [Hardcoded Secret and XML-RPC Bypass]
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was found in the `server-php/config/conf.d/wordpress.conf` file, which was used to bypass the blocking of `/xmlrpc.php`.
**Learning:** Hardcoded credentials or tokens should never be stored in configuration files or code. It introduces a critical vulnerability where an attacker gaining access to the config or code would instantly compromise the system. Additionally, XML-RPC is largely obsolete in modern WordPress and an attack vector for brute force and DDoS.
**Prevention:** Do not hardcode secrets in source files. Unconditionally block legacy and high-risk endpoints like `/xmlrpc.php` (`deny all;`). If access is required, rely on robust, dynamic authentication mechanisms.
