## 2025-02-14 - [CRITICAL] Hardcoded Secret and Authorization Bypass via Nginx XML-RPC

**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was present in `server-php/config/conf.d/wordpress.conf`. It bypassed the XML-RPC block (which was intended to deny access) if the `token` URL query parameter matched the secret.

**Learning:** Hardcoding secrets directly in server configurations (like Nginx) bypasses proper authentication mechanisms and secrets management. It can easily lead to authorization bypass because the configuration files are typically checked into source control and visible to all developers, creating a direct attack vector against specific endpoints (e.g., XML-RPC in WordPress, which is often targeted for brute force and amplification attacks).

**Prevention:** Never hardcode secrets in infrastructure or application configurations. Ensure that external endpoints like XML-RPC are either fully disabled or secured using robust, centralized authentication mechanisms (e.g., proper upstream authorization endpoints, WAF rules, or identity providers).
