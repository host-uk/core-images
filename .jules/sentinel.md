## 2024-06-06 - [Fix Hardcoded Secret in Nginx XML-RPC Bypass]
**Vulnerability:** A hardcoded secret token (`xrpc-9f8e7d6c5b4a`) was used in `server-php/config/conf.d/wordpress.conf` to bypass the block on `/xmlrpc.php`.
**Learning:** Hardcoding secrets directly in configuration files exposes the system to unauthorized access if the source code is compromised or if the configuration is inadvertently shared. The token acts as a static backdoor.
**Prevention:** Never hardcode secrets in configuration files. If an endpoint needs to be blocked, block it unconditionally. If conditional access is required, implement dynamic authentication upstream or inject secrets securely via environment variables at runtime.
