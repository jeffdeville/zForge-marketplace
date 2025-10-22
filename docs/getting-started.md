# Getting Started with zForge Marketplace

This guide will help you install the zForge marketplace and get started with your first plugin.

## Prerequisites

Before you begin, ensure you have:

- **Claude Code CLI** - Version 0.1.0 or later
- **Git** - For cloning plugin repositories
- **Node.js** (optional) - For some plugins that use JavaScript tools
- **Python** (optional) - For plugins requiring Python tools

## Installation

### Step 1: Add the Marketplace

```bash
claude plugin marketplace add zforge
```

This registers the zForge marketplace with your Claude Code installation.

### Step 2: Browse Available Plugins

```bash
claude plugin marketplace browse zforge
```

Or visit the [Plugin Catalog](./plugin-catalog.md) to see all available plugins with descriptions.

### Step 3: Install Your First Plugin

We recommend starting with the CADI Security Audit plugin:

```bash
claude plugin install cadi-audit@zforge
```

This will:
1. Clone the plugin repository
2. Verify the plugin manifest
3. Install commands, agents, and skills
4. Check for required dependencies

### Step 4: Verify Installation

```bash
claude plugin list
```

You should see `cadi-audit` in the list of installed plugins.

## Your First Audit

Let's run a CADI security audit on a sample project:

### Option 1: Using the Command

```bash
# Navigate to your project
cd /path/to/your/multi-tenant-app

# Run the audit
/cadi-audit
```

### Option 2: Using Natural Language (Agent Skills)

Simply start a conversation:

```
You: "I want to audit my Django app for cross-account data isolation issues"
```

Claude will automatically activate the CADI audit skill and guide you through the process.

### What to Expect

The audit will:
1. **Detect your tech stack** (e.g., Django + PostgreSQL)
2. **Identify tenancy patterns** (e.g., account_id foreign keys)
3. **Analyze read paths** (database queries that might leak data)
4. **Analyze write paths** (validation gaps in write operations)
5. **Generate reports** in `cadi-findings/` directory

Typical runtime: 30-60 minutes for medium-sized applications.

## Understanding Plugin Dependencies

Some plugins require additional tools:

### CADI Audit Requirements

**Required:**
- **Serena MCP Server** - For LSP-based code analysis

Install Serena:
```bash
claude mcp add -s local serena -- uvx --from git+https://github.com/oraios/serena \
  serena start-mcp-server --context ide-assistant --project $(pwd)
```

**Optional:**
- **xlsx skill** - For Excel checklist generation

Without xlsx, a Markdown checklist will be generated instead.

## Configuration

### Plugin Settings

Some plugins support configuration via environment variables or config files. Check individual plugin documentation for details.

### Marketplace Updates

To get the latest plugin versions:

```bash
# Update marketplace catalog
claude plugin marketplace sync zforge

# Update specific plugin
claude plugin update cadi-audit@zforge

# Update all plugins
claude plugin update --all
```

## Troubleshooting

### Plugin Not Found

**Problem:** `Error: Plugin 'cadi-audit' not found in marketplace 'zforge'`

**Solution:**
1. Verify marketplace is added: `claude plugin marketplace list`
2. Sync the marketplace: `claude plugin marketplace sync zforge`
3. Check spelling of plugin name

### Dependency Missing

**Problem:** `Error: Required MCP server 'serena' not found`

**Solution:**
1. Check plugin requirements: `claude plugin info cadi-audit@zforge`
2. Install missing dependencies (see above)
3. Verify installation: `claude mcp list`

### Command Not Found

**Problem:** `/cadi-audit` command not recognized

**Solution:**
1. Verify plugin is installed: `claude plugin list`
2. Restart Claude Code: `claude restart`
3. Check command path in plugin manifest

### Permission Errors

**Problem:** `Error: Permission denied when installing plugin`

**Solution:**
1. Check file permissions in `~/.claude/plugins/`
2. Run with appropriate permissions
3. Check disk space availability

## Next Steps

Now that you have the marketplace installed:

1. **Explore plugins** - Browse the [Plugin Catalog](./plugin-catalog.md)
2. **Learn patterns** - Read [Usage Examples](./usage-examples.md)
3. **Build your own** - Check the [Contributing Guide](./contributing.md)
4. **Understand architecture** - Review [Architecture Documentation](./architecture.md)

## Getting Help

If you encounter issues:

1. Check plugin-specific documentation in each plugin's repository
2. Search existing [issues](https://github.com/jeffdeville/zForge-marketplace/issues)
3. Join discussions in the repository
4. File a new issue with details about your problem

## Best Practices

### Keep Plugins Updated

```bash
# Weekly routine
claude plugin marketplace sync zforge
claude plugin update --all
```

### Review Changes

Before updating, check the changelog:
```bash
claude plugin info cadi-audit@zforge --changelog
```

### Manage Dependencies

Keep track of which plugins require which MCP servers and skills:
```bash
claude plugin info cadi-audit@zforge --dependencies
```

### Clean Up

Remove unused plugins to keep your environment clean:
```bash
claude plugin uninstall unused-plugin@zforge
```

## Resources

- [Plugin Catalog](./plugin-catalog.md) - All available plugins
- [Usage Examples](./usage-examples.md) - Common workflows
- [Contributing Guide](./contributing.md) - Add your own plugins
- [Architecture](./architecture.md) - How the marketplace works
