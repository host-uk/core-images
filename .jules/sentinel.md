# Sentinel's Journal

## 2025-02-18 - Incorrect Nginx Config Deployment
**Vulnerability:** The `server-php` Dockerfile was overwriting the main `/etc/nginx/nginx.conf` with a server-block fragment, which prevents Nginx from starting correctly (missing events/http context).
**Learning:** Configurations in `config/` are fragments (server blocks) and must be placed in `conf.d/` while relying on the base image's main configuration.
**Prevention:** Verify if Nginx configurations contain top-level blocks (`events`, `http`) before replacing the main config. Use `conf.d/default.conf` for site-specific configurations.
