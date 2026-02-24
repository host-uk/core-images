## 2025-02-18 - Hardcoded Secret in Nginx Config
**Vulnerability:** Found a hardcoded secret token `xrpc-9f8e7d6c5b4a` in `server-php/config/conf.d/wordpress.conf` used to bypass XML-RPC blocking.
**Learning:** Configuration files, especially for web servers like Nginx, can be overlooked sources of hardcoded secrets. Developers might add "backdoors" for convenience that become security risks.
**Prevention:** Always scan configuration files for secrets. Use environment variables or separate secret files for sensitive tokens, never commit them to the repo. If an endpoint is meant to be blocked, block it unconditionally unless there is a strong, secure requirement to allow it.
