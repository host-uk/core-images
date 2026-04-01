## 2025-02-18 - [Hardcoded Secrets in Nginx Config]
**Vulnerability:** A hardcoded XML-RPC bypass token (`xrpc-9f8e7d6c5b4a`) was found directly in `server-php/config/conf.d/wordpress.conf`.
**Learning:** Developers sometimes use hardcoded query parameters in Nginx `if` blocks to create "hidden" backdoors for maintenance or legacy API access, bypassing standard authentication. This is dangerous because Nginx configs are often checked into version control.
**Prevention:** Never hardcode secrets in Nginx configurations. If an endpoint needs protection, use proper upstream authentication, IP allowlisting, or environment variables (if supported by the startup script, e.g., via `envsubst`). For XML-RPC, it's safer to block it entirely if not strictly needed.
