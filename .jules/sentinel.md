## 2024-07-08 - [Hardcoded Secret Bypass in Nginx]
**Vulnerability:** A hardcoded secret token (`xrpc-9f8e7d6c5b4a`) was found in the Nginx configuration (`wordpress.conf`) to bypass the XML-RPC block via `$arg_token`.
**Learning:** Nginx configurations in this codebase sometimes implement custom authentication/bypass logic using hardcoded tokens in `$arg_token` variables, which exposes secrets in plaintext and bypasses proper upstream authentication.
**Prevention:** Strictly prohibit hardcoded secrets in configuration files. Replace token checks with unconditional blocks (`deny all;`) or proper authentication mechanisms at the application level. Disable logging (`access_log off; log_not_found off;`) for unconditionally blocked endpoints to prevent log flooding.
