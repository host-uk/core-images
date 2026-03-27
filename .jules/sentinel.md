## 2024-05-24 - [Remove Hardcoded Secrets from Nginx Conf]
**Vulnerability:** A hardcoded token `xrpc-9f8e7d6c5b4a` was found in the `server-php/config/conf.d/wordpress.conf` file to bypass the XML-RPC block.
**Learning:** Hardcoded secrets in Nginx configuration files are a security risk as they can be discovered in source control.
**Prevention:** Remove the hardcoded token and unconditionally block XML-RPC.