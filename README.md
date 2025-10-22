# zForge Workshops Marketplace

Collection of domain-specific workshops built with [Claude Code Agent Forge](https://github.com/jeffdeville/agent-forge).

## Available Workshops

### 🔒 CADI Security Audit (v1.0.0)

Automated Cross-Account Data Isolation security auditing for multi-tenant codebases.

**Install:**
```bash
/plugin marketplace add https://github.com/jeffdeville/zForge-marketplace
/plugin install cadi-audit
```

**Features:**
- Auto-detect tech stack and tenancy configuration
- LSP-based call graph analysis via Serena MCP
- Concurrent read/write path audits
- Proof-of-concept exploit generation
- Comprehensive reports (markdown + Excel)

**Repo:** [zForge-cadi-audit](https://github.com/jeffdeville/zForge-cadi-audit)

---

## Using This Marketplace

### Add Marketplace

```bash
/plugin marketplace add https://github.com/jeffdeville/zForge-marketplace
```

### Browse & Install

```bash
/plugin marketplace list
/plugin install <workshop-name>
```

### Update Workshops

```bash
/plugin uninstall <workshop-name>
/plugin install <workshop-name>
```

## Workshop Philosophy

Each zForge workshop is:
- **Independent** - Separate repo with own versioning
- **Production-ready** - Not just examples, actual tools
- **Domain-specific** - Focused on solving one problem well
- **Plugin-compatible** - Easy install via Claude Code plugin system

## Building Your Own

Want to create a zForge workshop?

1. Clone [Agent Forge](https://github.com/jeffdeville/agent-forge)
2. Use `/new-project` to scaffold your workshop
3. Build with Claude Code (Skills, Commands, Agents)
4. Add `.claude-plugin/plugin.json`
5. Submit PR to this marketplace

See [Agent Forge documentation](https://github.com/jeffdeville/agent-forge) for details.

## Coming Soon

- 📝 **API Documentation Generator** - Generate comprehensive API docs from code
- ⚡ **Performance Profiler** - Identify performance bottlenecks
- 🧪 **Test Coverage Analyzer** - Find gaps in test coverage
- 📊 **Data Pipeline Auditor** - Validate data transformation pipelines

## License

MIT - See individual workshop repos for details.

---

Built with [Claude Code](https://claude.com/claude-code) using [Agent Forge](https://github.com/jeffdeville/agent-forge).
