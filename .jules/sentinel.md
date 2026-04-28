## 2025-04-28 - Remove Hardcoded XML-RPC Secret By Default
**Vulnerability:** A hardcoded secret ('xrpc-9f8e7d6c5b4a') was used in `server-php/config/conf.d/wordpress.conf` to bypass the XML-RPC block (`/xmlrpc.php?token=...`). Hardcoded secrets pose a critical security risk and act as a backdoor.
**Learning:** In Nginx configs, developers sometimes leave backdoor tokens to bypass security rules during testing, which make it into production. The XML-RPC endpoint in WordPress is a notorious vector for brute-force attacks and DDoS.
**Prevention:** Completely deny all access to XML-RPC by default using `deny all;`. If access is required, it must use proper upstream authentication or IP allowlisting, not static hardcoded tokens in config files.
