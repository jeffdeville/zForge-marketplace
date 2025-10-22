# Plugin Catalog

Complete list of plugins available in the zForge marketplace.

## Security & Auditing

### CADI Security Audit

**Name:** `cadi-audit`
**Version:** 1.0.0
**Complexity:** Advanced
**Estimated Time:** 30-60 minutes

**Description:**
Automated Cross-Account Data Isolation (CADI) security auditing for multi-tenant codebases. Uses LSP-based call graph analysis to identify vulnerabilities where data from one account can leak to another.

**Features:**
- Auto-detects technology stack and tenancy configuration
- Concurrent read and write path audits
- LSP-based call graph tracing via Serena MCP
- Proof-of-concept exploit script generation
- Comprehensive markdown reports
- Excel checklist output (requires xlsx skill)

**Supported Languages:**
- Python (Django, Flask, FastAPI)
- Ruby (Rails, Sinatra)
- JavaScript/TypeScript (Express, NestJS)
- Java (Spring Boot)
- Go (various frameworks)
- PHP (Laravel, Symfony)

**Supported Frameworks:**
- Django, Rails, Express, Spring Boot, Laravel, and more

**Dependencies:**
- **Required:** Serena MCP server
- **Optional:** xlsx skill

**Installation:**
```bash
claude plugin install cadi-audit@zforge
```

**Quick Start:**
```bash
# Command-based
/cadi-audit

# Natural language (auto-activation)
"Run a CADI audit on my Django application"
```

**Resources:**
- [Repository](https://github.com/jeffdeville/zForge-cadi-audit)
- [Getting Started Guide](https://github.com/jeffdeville/zForge-cadi-audit#readme)
- [Setup Serena MCP](https://github.com/jeffdeville/zForge-cadi-audit/blob/main/SETUP_SERENA.md)

**When to Use:**
- Auditing multi-tenant SaaS applications
- Verifying account isolation before production launch
- Compliance requirements (SOC2, HIPAA data isolation)
- Post-refactoring security validation
- Investigating reported data leakage incidents

**Output:**
- `cadi-findings/write-path-report.md` - Database write vulnerabilities
- `cadi-findings/read-path-report.md` - Database read vulnerabilities
- `cadi-findings/summary-report.md` - Executive summary with priorities
- `cadi-findings/CADI-Checklist-Completed.xlsx` - Audit checklist (optional)
- Proof-of-concept exploit scripts

---

## Coming Soon

More plugins are in development. Check back soon for:

### API Documentation Generator
Automated API documentation with OpenAPI/Swagger generation

### Performance Profiler
Application performance analysis and optimization recommendations

### Database Migration Validator
Multi-tenant safe migration analysis

### Test Coverage Analyzer
Multi-tenant test coverage gaps identification

---

## Plugin Categories

### Security
- **cadi-audit** - Cross-account data isolation auditing

### Auditing
- **cadi-audit** - Multi-tenant security auditing

---

## Quick Reference

| Plugin | Category | Complexity | Time | Key Feature |
|--------|----------|------------|------|-------------|
| cadi-audit | Security | Advanced | 30-60min | LSP-based call graph analysis |

---

## Plugin Comparison

### When to use CADI Audit vs Traditional Security Scanners

**Use CADI Audit when:**
- You have multi-tenant architecture
- You need data isolation verification
- You want call graph-based analysis
- You need proof-of-concept exploits

**Use Traditional Scanners (SAST/DAST) when:**
- You need general vulnerability detection
- You want dependency vulnerability scanning
- You need compliance rule checking
- You want CI/CD integration

**Best Practice:** Use both! CADI Audit complements traditional security tools by focusing specifically on multi-tenant data isolation.

---

## Filter by Criteria

### By Complexity Level

**Beginner:**
- (Coming soon)

**Intermediate:**
- (Coming soon)

**Advanced:**
- cadi-audit

### By Time Required

**Quick (< 15 minutes):**
- (Coming soon)

**Moderate (15-45 minutes):**
- (Coming soon)

**Extended (45+ minutes):**
- cadi-audit (30-60 minutes)

### By Language

**Python:**
- cadi-audit (Django, Flask, FastAPI)

**Ruby:**
- cadi-audit (Rails, Sinatra)

**JavaScript/TypeScript:**
- cadi-audit (Express, NestJS)

**Java:**
- cadi-audit (Spring Boot)

**Go:**
- cadi-audit

**PHP:**
- cadi-audit (Laravel, Symfony)

### By Framework

**Django:** cadi-audit
**Rails:** cadi-audit
**Express:** cadi-audit
**Spring Boot:** cadi-audit
**Laravel:** cadi-audit

---

## Installation Commands

```bash
# Install all security plugins
claude plugin install cadi-audit@zforge

# Install by category (when more plugins available)
# claude plugin install --category security @zforge
```

---

## Contributing

Want to add your plugin to the catalog? See the [Contributing Guide](./contributing.md).

---

## Feedback

Have suggestions for new plugins? [Open an issue](https://github.com/jeffdeville/zForge-marketplace/issues) with the "plugin-request" label.
