# zForge Marketplace Documentation

Welcome to the zForge marketplace documentation. This marketplace provides production-ready security and development tools built with Claude Code Agent Forge.

## Documentation Index

- **[Getting Started](./getting-started.md)** - Installation and setup guide
- **[Plugin Catalog](./plugin-catalog.md)** - Complete list of available plugins
- **[Contributing](./contributing.md)** - How to add your own plugins
- **[Architecture](./architecture.md)** - Marketplace design and structure
- **[Usage Examples](./usage-examples.md)** - Common workflows and patterns

## Quick Links

- [zForge Marketplace Repository](https://github.com/jeffdeville/zForge-marketplace)
- [Agent Forge](https://github.com/jeffdeville/agent-forge) - Tool for building plugins
- [Issue Tracker](https://github.com/jeffdeville/zForge-marketplace/issues)

## About zForge

zForge is a collection of domain-specific workshops built with Claude Code Agent Forge. Each plugin is:

- **Production-ready** - Thoroughly tested and documented
- **Focused** - Solves specific, well-defined problems
- **Independent** - Self-contained with clear dependencies
- **Shareable** - Easy to version control and distribute

## Philosophy

Each workshop is an independent repository, allowing:
- Version control for individual tools
- Easy updates without affecting other plugins
- Simple sharing across projects and teams
- Clear ownership and contribution paths

## Getting Help

- Browse the [FAQ section](#faq) below
- Check [individual plugin documentation](./plugin-catalog.md)
- [File an issue](https://github.com/jeffdeville/zForge-marketplace/issues) for bugs or feature requests
- Review [usage examples](./usage-examples.md) for common patterns

## FAQ

### How do I install the marketplace?

```bash
claude plugin marketplace add zforge
```

### How do I install a specific plugin?

```bash
claude plugin install plugin-name@zforge
```

### What are the prerequisites?

- Claude Code CLI installed
- Git configured
- Plugin-specific requirements (see individual plugin docs)

### How do I update plugins?

```bash
claude plugin update plugin-name@zforge
```

### Can I contribute my own plugins?

Yes! See the [Contributing Guide](./contributing.md) for details on how to add your plugins to the marketplace.

### What's the difference between commands, agents, and skills?

- **Commands** - Executable workflows you trigger explicitly (e.g., `/cadi-audit`)
- **Agents** - Specialized AI assistants for specific domains
- **Skills** - Knowledge packages that enable auto-activation based on conversation context

### How are plugins organized?

Plugins are grouped by category:
- **Security** - Security auditing and vulnerability scanning
- **Development** - Code generation and development tools
- **Documentation** - API docs and technical writing
- **Performance** - Profiling and optimization tools

See the [Plugin Catalog](./plugin-catalog.md) for the complete list.
