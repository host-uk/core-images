# Sentinel's Journal

## 2025-02-18 - Incorrect Nginx Config Deployment
**Vulnerability:** The `server-php` Dockerfile was overwriting the main `/etc/nginx/nginx.conf` with a server-block fragment, which prevents Nginx from starting correctly (missing events/http context).
**Learning:** Configurations in `config/` are fragments (server blocks) and must be placed in `conf.d/` while relying on the base image's main configuration.
**Prevention:** Verify if Nginx configurations contain top-level blocks (`events`, `http`) before replacing the main config. Use `conf.d/default.conf` for site-specific configurations.

## 2026-02-03 - CI Failure: FrankenPHP Asset Naming
**Vulnerability:** The CI build for `developer` image failed on `linux/arm64` because the `curl` command tried to download `frankenphp-linux-arm64`, but the official asset is named `frankenphp-linux-aarch64`.
**Learning:** `uname -m` outputs `aarch64` on ARM64 Linux systems. FrankenPHP uses this standard name for its release assets. Remapping it to `arm64` (via `sed`) broke the download.
**Prevention:** Verify release asset naming conventions before applying architecture remapping. Often `$(uname -m)` matches the asset name directly.
