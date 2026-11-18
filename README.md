# Lab 7 Unit II - Secure Design, Code Review and Vulnerability Analysis

Student: Aditey Mehra (2301730266) | B.Tech CSE (AI & ML), Section D, Semester 7 | K.R. Mangalam University

## Scope
Target: OWASP NodeGoat 1.3.0, commit c5cb68a7084e4ae7dcc60e6a98768720a81841e8.
A random, non-personal open-source training application was selected because no application was assigned.
All testing was performed locally on 127.0.0.1 in Docker. No public or third-party system was scanned.

## Environment and tool versions
- NodeGoat 1.3.0 in Docker (local image `lab7-nodegoat:local`), MongoDB 4.4/6, port 4000 only.
- SonarQube 9.9.8.100196 with scanner CLI 3.1.0.1141; project `lab7_nodegoat`.
- OWASP ZAP 2.17.0 in daemon mode, API bound to 127.0.0.1:8090.
- Docker build performed `npm audit`; 902 dependency vulnerabilities were reported.

## Reproduction summary
1. Clone the target commit and build the provided Dockerfile.
2. Start MongoDB and NodeGoat bound to localhost only; seed with the repository's own reset script.
3. Run SonarQube and export issues/hotspots/measures via its REST API.
4. Run ZAP spider and targeted active scans against http://127.0.0.1:4000 only.
5. Review the listed source files manually and complete the checklist.

## Results summary
SonarQube: 80 issues (17 bugs, 63 code smells), 18 security hotspots, quality gate OK.
ZAP: 226 raw alerts; 180 distinct after de-duplication (High 1, Medium 46, Low 99, Informational 34).
Manual review: 18 checks - 1 Pass, 15 Fail, 2 Not Verified.

## Ethical-use boundary
Only the local, disposable instance was tested. No credentials, API keys, session cookies, private keys, production data, database dumps or unredacted traffic are stored in this repository. ZAP and SonarQube API keys were used only in local process configuration and are not committed.
