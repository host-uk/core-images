## 2026-05-16 - [CRITICAL] Remove Hardcoded XML-RPC Secret Bypass
**Vulnerability:** A hardcoded token (`$arg_token = "xrpc-9f8e7d6c5b4a"`) was present in `server-php/config/conf.d/wordpress.conf`, acting as a backdoor to bypass the default block on `/xmlrpc.php`.
**Learning:** Hardcoding secrets directly in configuration files exposes them in version control and creates backdoor access. `xmlrpc.php` is a frequent attack vector and should be denied unconditionally unless explicitly required by a legacy service, rather than protected with static tokens.
**Prevention:** Unconditionally block high-risk endpoints like `/xmlrpc.php` (`deny all;`) and disable logging for them to prevent log spam. Never hardcode tokens or credentials in Nginx configurations.
