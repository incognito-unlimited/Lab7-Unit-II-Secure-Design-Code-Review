# SAST - SonarQube Summary

| SAST metric | Actual value |
|---|---|
| Scan status | Success (SonarQube 9.9.8.100196; scanner CLI 3.1.0.1141) |
| Project and commit | lab7_nodegoat / 1.3.0 / c5cb68a7084e4ae7dcc60e6a98768720a81841e8 |
| Bugs | 17 |
| Vulnerabilities | 0 (SonarQube metric) |
| Security hotspots | 18 (all TO_REVIEW) |
| Code smells | 63 |
| Quality gate | OK (passed) |
| Total issues / severity | 80 total: Critical 11, Major 46, Minor 18, Info 5 |

Export files: `sonarqube-results/issues.json`, `hotspots.json`, `measures.json`, `quality-gate.json`, `scanner-output.txt`.

Top hotspot rules reviewed: S5852 (ReDoS), S4721 (OS command), S1523 (dynamic code), S2245 (weak PRNG), docker:S6470 (recursive COPY).
