# DAST - OWASP ZAP Summary

| DAST metric | Actual value |
|---|---|
| Tool and version | OWASP ZAP 2.17.0 (daemon mode, API key used locally only) |
| Target and scope | http://127.0.0.1:4000 only; spider + 5 targeted active scans |
| Authentication coverage | Unauthenticated / partial - public and login routes only |
| High risk | 1 distinct (DOM-based XSS on /login, pending manual validation) |
| Medium risk | 46 distinct |
| Low risk | 99 distinct |
| Informational | 34 distinct |
| Status and duration | Spider complete; 5 active scans completed (status 100); 226 raw / 180 distinct alerts |

Raw ZAP alert export was de-duplicated by alert name + URL + parameter before counting. The only High alert is a DOM-based XSS report on `/login`; it was not manually confirmed in a browser and is recorded as pending validation.

Sanitised exports: `zap-reports/alerts-sanitized.json`, `zap-reports/alerts-sanitized.csv`, `zap-reports/spider-results.json`, `zap-reports/sites.json`.
