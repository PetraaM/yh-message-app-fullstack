# Phase 3 – Review

## Tools Used

- npm audit for dependency analysis, directly in terminal of the VS code, phase 2. of SDLC (code)
- Dependabot for continous dependency monitoring in GitHub, phase 6. of SDLC (operate)
- CodeQL for static code analysis

## Findings

### Vulnerable Dependencies

Dependabot identified 16 dependency vulnerabilities, including issues in jsonwebtoken, tar, qs, vite and esbuild.

OWASP: A06 – Vulnerable and Outdated Components

### Missing Rate Limiting

CodeQL identified endpoints performing database operations without rate limiting.

OWASP: A04 – Insecure Design

### Permissive CORS Configuration

CodeQL identified a permissive CORS configuration using origin: "\*".

OWASP: A05 – Security Misconfiguration

## Recommendations

- Upgrade vulnerable dependencies
- Implement rate limiting
- Restrict CORS to trusted domains
- Continue dependency monitoring using Dependabot

## Conclusion

The review identified several security findings, including vulnerable dependencies, missing rate limiting and permissive CORS configuration. However, no findings were identified that immediately compromise the application's confidentiality, integrity or availability.

The review highlighted areas where the security of the application can be improved, particularly through dependency updates, rate limiting and configuration hardening.
Different security review methods found different problems. No single tool found everything. That is why its important to use multiple approaches in secure development.

## Presentation

[Phase 3 Presentation (Canva)](https://canva.link/a0tqjpfpleicqdw)
