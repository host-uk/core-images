## 2025-02-17 - [Hardcoded Secrets in Nginx Config]
**Vulnerability:** Found a hardcoded XML-RPC token in `server-php/config/conf.d/wordpress.conf`.
**Learning:** Nginx configurations are often overlooked for secrets. Developers might use `if ($arg_token = ...)` which is extremely insecure as the token is visible in the repo.
**Prevention:** Use environment variables (via `envsubst` or Lua) or external authentication services. Never hardcode tokens in static config files.
