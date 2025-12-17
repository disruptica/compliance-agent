# Installation Guide

This guide covers how to install the Kompliance-X plugin for Claude Code using the plugin system, as well as legacy manual installation methods.

## Plugin Installation (Recommended)

### Prerequisites

- Claude Code installed on your machine
- Basic familiarity with command-line tools

### From GitHub Repository

The easiest way to install this plugin is directly from GitHub:

1. **Add this repository as a marketplace**:
   ```shell
   /plugin marketplace add disruptica/claude-plugins
   ```

2. **Install the plugin**:
   ```shell
   /plugin install kompliance-x@disruptica-plugins
   ```

   Or browse and install interactively:
   ```shell
   /plugin
   ```
   Select "Browse Plugins" → Find "kompliance-x" → Install

3. **Restart Claude Code** to activate the plugin

4. **Verify installation**:
   - Run `/help` to see if the plugin's features are available
   - Try: "Can you audit my project for compliance?"

### For Local Development/Testing

If you're developing or testing changes to this plugin:

1. **Fork or clone this repository**:
   ```bash
   git clone https://github.com/disruptica/claude-plugins.git
   cd claude-plugins
   ```

2. **Add the local repository as a marketplace**:
   ```shell
   /plugin marketplace add /absolute/path/to/claude-plugins
   ```

3. **Install the plugin**:
   ```shell
   /plugin install kompliance-x@disruptica-plugins
   ```

4. **After making changes**, reinstall to test:
   ```shell
   /plugin uninstall kompliance-x@disruptica-plugins
   /plugin install kompliance-x@disruptica-plugins
   ```

5. **Restart Claude Code** to load your changes

### Installation Scopes

You can install plugins at different scopes:

- **User scope** (default): Available across all your projects
  ```shell
  /plugin install kompliance-x@marketplace
  ```

- **Project scope**: Shared with your team via version control
  ```shell
  /plugin install kompliance-x@marketplace --scope project
  ```

- **Local scope**: Project-specific, gitignored
  ```shell
  /plugin install kompliance-x@marketplace --scope local
  ```

## Manual Installation (Legacy)

If you prefer not to use the plugin system, you can install the skill manually:

### Project-Specific Installation

Install for a specific project:

```bash
# Navigate to your project
cd /path/to/your/project

# Create skills directory if it doesn't exist
mkdir -p .claude/skills

# Copy the skill
cp -r /path/to/claude-plugins/skills/kompliance-x .claude/skills/

# The skill is now available in this project!
```

### Global Installation

Install for all your projects:

```bash
# Create personal skills directory if it doesn't exist
mkdir -p ~/.claude/skills

# Copy the skill
cp -r /path/to/claude-plugins/skills/kompliance-x ~/.claude/skills/

# The skill is now available in all your projects!
```

## Plugin Management

### Update a Plugin

```shell
/plugin update kompliance-x@marketplace
```

Or reinstall:
```shell
/plugin uninstall kompliance-x@marketplace
/plugin install kompliance-x@marketplace
```

### Disable a Plugin (without uninstalling)

```shell
/plugin disable kompliance-x@marketplace
```

### Re-enable a Plugin

```shell
/plugin enable kompliance-x@marketplace
```

### Uninstall a Plugin

```shell
/plugin uninstall kompliance-x@marketplace
```

## Verification

After installation, verify the plugin is working:

1. **Check available features**:
   ```shell
   /help
   ```

2. **Test the skill directly**:
   ```
   "Can you audit my project for compliance?"
   ```

3. **Check plugin status**:
   ```shell
   /plugin
   ```
   Select "Manage Plugins" to see installed plugins

## Troubleshooting

### Plugin Not Appearing

**Problem:** Plugin doesn't show up after installation

**Solutions:**
1. Restart Claude Code (`/exit` then restart)
2. Verify installation: `/plugin` → "Manage Plugins"
3. Check marketplace is added: `/plugin` → "Manage Marketplaces"
4. Try reinstalling: `/plugin uninstall` then `/plugin install`

### Skill Not Being Used

**Problem:** Claude doesn't use the kompliance-x skill

**Solutions:**
1. Ask explicitly: "Can you audit my project for compliance?"
2. Mention specific frameworks: "Can you check if we comply with GDPR?"
3. Check skill activation in the skill description
4. Verify the skill files are in the correct location

### Marketplace Not Found

**Problem:** Cannot add local marketplace

**Solutions:**
1. Verify the path is correct (use absolute or relative paths)
2. Check that `.claude-plugin/marketplace.json` exists
3. Ensure the marketplace JSON is valid
4. Try using an absolute path: `/plugin marketplace add /absolute/path/to/marketplace`

### Permission Errors

**Problem:** Permission denied when installing

**Solutions:**
1. Check file permissions on the plugin directory
2. Ensure you have write access to the installation location
3. For global installs, you may need appropriate permissions

## Development Workflow

For plugin developers working on this plugin:

1. **Make changes** to the plugin files
2. **Uninstall the current version**:
   ```shell
   /plugin uninstall kompliance-x@compliance-plugin-marketplace
   ```
3. **Reinstall** to test changes:
   ```shell
   /plugin install kompliance-x@compliance-plugin-marketplace
   ```
4. **Restart Claude Code** to load the updated plugin
5. **Test** your changes

## Team Installation

To set up this plugin for your team:

1. **Add plugin configuration** to your repository's `.claude/settings.json`:
   ```json
   {
     "plugins": {
       "marketplaces": {
         "compliance-marketplace": "<marketplace-url>"
       },
       "installed": [
         {
           "name": "kompliance-x",
           "marketplace": "compliance-marketplace",
           "enabled": true
         }
       ]
     }
   }
   ```

2. **Team members** trust the repository folder and the plugin installs automatically

## Requirements

- Claude Code CLI installed
- Git (for cloning this repo)
- Basic command-line knowledge

## Next Steps

After installation:

1. Read [README.md](README.md) for usage examples
2. Try an audit on a test project first
3. Review the skill's `examples.md` for sample outputs
4. Customize `detection-criteria.md` if needed for your use case

## Support

- Check [README.md](README.md) for general documentation
- Review `skills/kompliance-x/examples.md` for sample audit reports
- Consult `skills/kompliance-x/detection-criteria.md` for framework detection logic
- Report issues or contribute improvements via GitHub

---

Happy auditing! 🔒
