# Prioritised Remediation Plan

| Priority | Finding IDs | Recommended action | Owner / role | Timeframe | Verification |
|---|---|---|---|---|---|
| P1 - Urgent | F-01,F-03,F-04,F-05,F-07,F-09,F-12 | Remove plaintext passwords, enforce admin checks, remove $where/SSRF, externalise secrets, patch dependencies. | Application owner | Before any deployment | Retest source review and SAST/DAST. |
| P2 - High | F-02,F-06,F-08,F-10,F-11 | Regenerate sessions, allowlist redirects, fix regex, enable helmet/TLS/CSRF, strengthen password policy. | Backend developer | Next sprint | Re-run ZAP and targeted unit tests. |
| P3 - Planned | F-13 | Add structured audit logging with redaction and alerting. | Platform / DevOps | Following release | Review log samples and access controls. |
| P4 - Hardening | All | Add SAST/DAST and dependency audit gates to CI; remove training defaults. | Security champion | Continuous | Monitor quality gate and scan trends. |
