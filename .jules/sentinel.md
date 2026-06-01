## 2026-06-01 - [Hardcoded XML-RPC Secret Bypass]
**Vulnerability:** A hardcoded token `xrpc-9f8e7d6c5b4a` was present in `server-php/config/conf.d/wordpress.conf` which allowed bypassing the XML-RPC block.
**Learning:** Hardcoding secrets or bypass tokens in server configuration files creates a critical vulnerability.
**Prevention:** Remove hardcoded secrets from configuration files and unconditionally block sensitive endpoints like XML-RPC unless explicitly required and secured with a proper mechanism.
