
## 2024-04-02 - [CRITICAL] Removed hardcoded XML-RPC bypass token
**Vulnerability:** A hardcoded secret token (`xrpc-9f8e7d6c5b4a`) was present in `server-php/config/conf.d/wordpress.conf` which allowed bypassing the XML-RPC block (`/xmlrpc.php`). This means anyone with the source code could bypass the security control.
**Learning:** Hardcoded tokens or passwords in Nginx configurations (or any source code) should be strictly avoided. Authentication logic shouldn't rely on static strings in proxy/webserver configurations, as they are often exposed or leak via version control.
**Prevention:** Remove hardcoded conditional blocks and replace them with unconditional `deny all;` blocks. If bypasses are necessary, they should rely on secure upstream authentication mechanisms instead of hardcoded `$arg_token` matching.
