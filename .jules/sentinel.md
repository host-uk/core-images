## 2024-05-19 - [Initialization]
**Vulnerability:** N/A
**Learning:** N/A
**Prevention:** N/A

## 2026-05-19 - [Fix hardcoded XML-RPC secret bypass]
**Vulnerability:** A hardcoded authentication token bypass was found for `/xmlrpc.php` allowing potentially malicious XML-RPC access by using `?token=xrpc-9f8e7d6c5b4a`.
**Learning:** Implementing security bypasses with hardcoded tokens in Nginx configuration directly undermines defense in depth.
**Prevention:** Never use hardcoded secrets in Nginx config files. If endpoints need protection or conditional access, use proper upstream authentication or block completely (`deny all;`) if unneeded.
