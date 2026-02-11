## 2024-05-23 - Hardcoded Secret in Nginx Config
**Vulnerability:** Found a hardcoded token 'xrpc-9f8e7d6c5b4a' in 'server-php/config/conf.d/wordpress.conf' used to bypass XML-RPC blocking.
**Learning:** Hardcoding secrets in config files for 'convenience' is a common pattern that gets committed to version control. Nginx configs often lack environment variable support, leading to this anti-pattern.
**Prevention:** Use environment variables and envsubst at runtime to inject secrets, or use a proper secret management system. Never commit secrets to the repo.
