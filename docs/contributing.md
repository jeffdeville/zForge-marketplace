# Contributing to zForge Marketplace

Thank you for your interest in contributing to the zForge marketplace! This guide will help you add your own plugins or improve existing ones.

## Ways to Contribute

1. **Add a new plugin** - Share your Claude Code plugin with the community
2. **Improve documentation** - Help others understand and use plugins better
3. **Report bugs** - Help us identify and fix issues
4. **Suggest features** - Propose new plugins or improvements

## Adding Your Plugin

### Prerequisites

Before submitting a plugin:

1. **Test thoroughly** - Ensure it works reliably
2. **Document completely** - README, usage examples, troubleshooting
3. **Follow standards** - Use the plugin template structure
4. **License clearly** - Include appropriate open-source license

### Step 1: Prepare Your Plugin

Your plugin should follow this structure:

```
your-plugin/
├── .claude-plugin/
│   ├── plugin.json              # Required manifest
│   ├── commands/                # Optional commands
│   │   └── command-name.md
│   ├── agents/                  # Optional agents
│   │   └── agent-name.md
│   └── skills/                  # Optional skills
│       └── skill-name/
│           └── SKILL.md
├── README.md                    # Required documentation
├── CHANGELOG.md                 # Version history
└── LICENSE                      # Required license file
```

### Step 2: Create plugin.json

Use our template (see [templates/plugin.json](../templates/plugin.json)):

```json
{
  "name": "your-plugin",
  "version": "1.0.0",
  "description": "Brief description of what your plugin does",
  "author": {
    "name": "Your Name",
    "url": "https://github.com/yourusername"
  },
  "repository": "https://github.com/yourusername/your-plugin",
  "homepage": "https://github.com/yourusername/your-plugin#readme",
  "license": "MIT",
  "keywords": [
    "keyword1",
    "keyword2",
    "category-name"
  ],
  "commands": ["./commands/your-command.md"],
  "skills": ["./skills/your-skill"],
  "metadata": {
    "complexity": "beginner|intermediate|advanced",
    "estimated_time": "X-Y minutes",
    "supported_languages": ["python", "javascript"],
    "supported_frameworks": ["django", "express"],
    "dependencies": {
      "required": {
        "mcp_servers": ["server-name"]
      },
      "optional": {
        "skills": ["skill-name"]
      }
    }
  }
}
```

**Required fields:**
- `name` - Kebab-case identifier
- `version` - Semantic versioning (1.0.0)
- `description` - Clear, concise description
- `author.name` - Your name or organization

**Recommended fields:**
- `author.url` - Link to your profile/website
- `repository` - Plugin source code location
- `homepage` - Documentation URL
- `license` - OSS license (MIT recommended)
- `keywords` - For discoverability
- `metadata` - Complexity, time, dependencies

### Step 3: Write Documentation

Your README.md should include:

```markdown
# Plugin Name

One-line description

## Features
- Key capability 1
- Key capability 2
- Key capability 3

## Installation
\`\`\`bash
claude plugin install your-plugin@zforge
\`\`\`

## Prerequisites
- Required tools
- Optional dependencies

## Quick Start
Basic usage example

## Detailed Usage
Step-by-step guide

## Examples
Real-world scenarios

## Configuration
Settings and options

## Troubleshooting
Common issues and solutions

## Contributing
How to contribute to your plugin

## License
MIT - see LICENSE file
```

### Step 4: Submit to Marketplace

1. **Fork the marketplace repository:**
   ```bash
   git clone https://github.com/jeffdeville/zForge-marketplace
   cd zForge-marketplace
   git checkout -b add-your-plugin
   ```

2. **Add your plugin to marketplace.json:**
   ```json
   {
     "name": "your-plugin",
     "description": "Brief description",
     "repository": "https://github.com/yourusername/your-plugin",
     "version": "1.0.0",
     "author": {
       "name": "Your Name",
       "url": "https://github.com/yourusername"
     },
     "homepage": "https://github.com/yourusername/your-plugin#readme",
     "license": "MIT",
     "keywords": ["keyword1", "keyword2"],
     "category": "category-name",
     "source": {
       "source": "github",
       "repo": "yourusername/your-plugin"
     },
     "commands": ["./commands/your-command.md"],
     "skills": ["./skills/your-skill"]
   }
   ```

3. **Update the plugin catalog:**
   Add an entry to `docs/plugin-catalog.md` following the existing format.

4. **Create a pull request:**
   ```bash
   git add .claude-plugin/marketplace.json docs/plugin-catalog.md
   git commit -m "Add your-plugin to marketplace"
   git push origin add-your-plugin
   ```

5. **Open PR on GitHub** with:
   - Clear description of your plugin
   - Link to plugin repository
   - Testing instructions
   - Any special requirements

## Plugin Quality Guidelines

### Code Quality

- **Clear structure** - Easy to navigate and understand
- **Error handling** - Graceful failures with helpful messages
- **Performance** - Reasonable execution time
- **Security** - No vulnerabilities or risky operations

### Documentation Quality

- **Comprehensive README** - All sections covered
- **Usage examples** - Real-world scenarios
- **Troubleshooting** - Common issues documented
- **Up-to-date** - Matches current implementation

### Testing

- **Manual testing** - Verify all features work
- **Edge cases** - Test error conditions
- **Different environments** - Multiple platforms/versions
- **Dependencies** - Verify required tools

## Plugin Categories

Choose the most appropriate category:

- **Security** - Security auditing, vulnerability scanning
- **Development** - Code generation, scaffolding, refactoring
- **Documentation** - API docs, technical writing, diagrams
- **Testing** - Test generation, coverage analysis
- **Performance** - Profiling, optimization, monitoring
- **Database** - Migrations, queries, optimization
- **DevOps** - CI/CD, deployment, infrastructure
- **Utilities** - General-purpose tools

Can't find a fit? Propose a new category in your PR.

## Review Process

Once you submit a PR:

1. **Automated checks** - CI validates manifest structure
2. **Manual review** - Maintainers test functionality
3. **Documentation review** - Check completeness and clarity
4. **Feedback** - Address any requested changes
5. **Approval** - Plugin added to marketplace
6. **Announcement** - Featured in release notes

Typical review time: 3-7 days

## Updating Your Plugin

To update an existing plugin:

1. **Update your plugin repository:**
   - Make changes
   - Update version in plugin.json
   - Update CHANGELOG.md
   - Tag release in git

2. **Update marketplace entry:**
   - Change version number
   - Update description if needed
   - Submit PR to marketplace

3. **Users get updates:**
   ```bash
   claude plugin update your-plugin@zforge
   ```

## Plugin Maintenance

### Versioning

Follow semantic versioning:
- **Major (1.0.0 → 2.0.0)** - Breaking changes
- **Minor (1.0.0 → 1.1.0)** - New features, backward compatible
- **Patch (1.0.0 → 1.0.1)** - Bug fixes

### Deprecation

If deprecating features:
1. Mark as deprecated in docs
2. Add warning messages
3. Provide migration guide
4. Wait one major version before removing

### Support

Maintain your plugin by:
- Responding to issues promptly
- Updating for new Claude Code versions
- Fixing reported bugs
- Adding requested features (when appropriate)

## Code of Conduct

We expect all contributors to:
- Be respectful and inclusive
- Provide constructive feedback
- Focus on what's best for the community
- Show empathy towards others

## Getting Help

Need assistance?
- Ask questions in [Discussions](https://github.com/jeffdeville/zForge-marketplace/discussions)
- Check existing [Issues](https://github.com/jeffdeville/zForge-marketplace/issues)
- Reach out to maintainers

## Recognition

Contributors are recognized in:
- Marketplace contributor list
- Release notes
- Plugin documentation (as author)

Thank you for contributing to zForge! 🚀
