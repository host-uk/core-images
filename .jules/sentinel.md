# Sentinel Journal - Security Learnings

This journal documents CRITICAL security learnings, vulnerability patterns, and architectural gaps discovered during security reviews.

## 2024-05-22 - Hardcoded Secrets in Configuration
**Vulnerability:** A hardcoded token (`xrpc-9f8e7d6c5b4a`) was found in the Nginx configuration to bypass XML-RPC blocks.
**Learning:** Developers sometimes implement "backdoors" or convenience bypasses for blocked features using hardcoded strings in configuration files, which are often checked into version control and visible to anyone with read access.
**Prevention:** Use environment variables for secrets, or better yet, implement proper authentication mechanisms (like OAuth or application passwords) instead of ad-hoc token checks in web server configs. For XML-RPC, it should generally be disabled unless specifically required by an external service.
