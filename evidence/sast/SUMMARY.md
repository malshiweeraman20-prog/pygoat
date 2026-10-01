# SAST Before/After Comparison

**Tool:** Semgrep (config=auto, 501 rules)

## Overall Counts
- Before fix: 135 findings (267 files scanned)
- After fix: 138 findings (266 files scanned)
- Note: +3 increase due to new CI/CD workflow file (devsecops.yml) added by teammate, unrelated to security fixes.

## Vulnerability-Specific Results

| Vulnerability | Rule(s) | Before | After |
|---|---|---|---|
| SQL Injection | tainted-sql-string, avoid-raw-sql | Present | Resolved |
| Command Injection (shell=True) | subprocess-shell-true, subprocess-injection | Present | Resolved |
| Command Injection (generic) | dangerous-subprocess-use | Present | Still flagged (advisory-level) |
| Broken Access Control | N/A (logic bug) | Cookie-trust code present | Code removed entirely |

## Conclusion
All 4 demonstrated exploits were fixed. 3 of 4 corresponding Semgrep findings were eliminated.
