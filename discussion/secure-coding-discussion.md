# Why Secure Coding Matters - Evidence-Based Discussion

| Evidence ID | Specific finding | Plausible consequence | Likelihood / preconditions | Severity rationale | Action |
|---|---|---|---|---|---|
| F-01 | Plaintext passwords | Database read exposes usable credentials for other services. | Requires DB/file access or backup exposure. | High impact because passwords are reusable. | Hash and salt all passwords. |
| F-04 / F-05 | NoSQL injection and SSRF | Attacker can query or modify records and reach internal HTTP services. | Authenticated user with request access. | Direct access to data and internal network pivot. | Typed queries; outbound allowlist and timeout. |
| F-03 | Missing admin check on benefits | Any logged-in user can change benefit start dates. | Requires any user account. | Integrity loss in HR-style records. | Enforce role checks server-side. |
| F-08 | ReDoS regex | A crafted value can hold the event loop busy. | Requires profile update access. | Availability impact on a single-process Node app. | Use linear-time regex and input limits. |
| F-07 / F-10 | XSS and absent headers | Script execution and clickjacking can target user sessions. | Requires victim interaction or stored input. | Browser-side compromise and trust loss. | Context-aware encoding, CSP, helmet, CSRF. |

Confidentiality: plaintext passwords (F-01), hardcoded keys (F-09) and the open redirect / SSRF paths (F-05, F-06) could expose credentials, session material or internal responses.
Integrity: missing admin checks (F-03) and `$where` injection (F-04) allow unauthorised modification of records.
Availability: the ReDoS pattern (F-08) and unbounded outbound requests (F-05) can exhaust the single-process Node.js event loop.
Authentication/authorisation: session fixation (F-02), weak password rules (F-11) and absent CSRF (F-10) weaken account and action controls.
Operational/business impact: an incident would require containment, code fixes, credential rotation and retesting; public exposure of personal or benefit data would harm trust. These are plausible consequences, not quantified losses.
Secure lifecycle: threat modelling found the trust-boundary flows early; manual review confirmed unsafe patterns; SAST and DAST provided independent coverage. Secure defaults, dependency maintenance and continuous scanning would prevent these defects from reaching production.
