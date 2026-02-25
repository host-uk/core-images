## 2024-05-22 - [Hardcoded Secrets in Config Files]
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was found in `server-php/config/conf.d/wordpress.conf` used to bypass XML-RPC blocking.
**Learning:** Configuration files (like Nginx configs) committed to the repository are visible to everyone. Hardcoding secrets in them defeats the purpose of access control.
**Prevention:** Use environment variables for secrets, or if not possible in the specific config format, use a template system (like `envsubst` in entrypoint) to inject secrets at runtime. Never commit secrets.
