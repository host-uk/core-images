## 2024-07-01 - [CRITICAL] Fix hardcoded token XML-RPC bypass
**Vulnerability:** Hardcoded token backdoor for XML-RPC (`$arg_token = "xrpc-9f8e7d6c5b4a"`).
**Learning:** Hardcoded strings in nginx configs for bypasses circumvent standard application authentication and are trivial to abuse.
**Prevention:** Unconditionally block sensitive endpoints at the webserver level or rely on robust authentication mechanisms, avoiding explicit hardcoded strings.
