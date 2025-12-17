# Quick Start Guide

Get the Kompliance-X plugin up and running in 2 minutes.

## Install from GitHub

1. **Open Claude Code**:
   ```bash
   claude
   ```

2. **Add the plugin marketplace**:
   ```shell
   /plugin marketplace add disruptica/claude-plugins
   ```

3. **Install the plugin**:
   ```shell
   /plugin install kompliance-x@disruptica-plugins
   ```

4. **Restart Claude Code** when prompted

5. **Test it**:
   ```
   "Can you audit my project for compliance?"
   ```

## What Happens Next?

1. Claude will analyze your codebase
2. It will ask questions to determine which compliance frameworks apply
3. You'll receive an executive summary with:
   - Compliance scores
   - Critical gaps
   - Actionable roadmap

## Common Commands

After installation:

- **Get help**: `/help`
- **Check plugin status**: `/plugin`
- **Update plugin**: `/plugin update kompliance-x@disruptica-plugins`
- **Uninstall**: `/plugin uninstall kompliance-x@disruptica-plugins`

## Example Usage

```
"Can you audit my project for compliance?"
```

```
"Check if my application complies with GDPR"
```

```
"Perform a compliance audit for data protection regulations"
```

## Plugin Structure

The plugin includes:

- **kompliance-x skill**: Automatically used when you ask about compliance
- **5 framework checklists**: GDPR, HIPAA, PCI-DSS, CCPA/CPRA, SOC 2
- **Smart detection**: Determines which frameworks apply to your project
- **Tiered reporting**: Executive summaries and detailed technical reports

## Next Steps

1. Read [INSTALL.md](INSTALL.md) for detailed installation options
2. Read [README.md](README.md) for full documentation
3. Check `skills/kompliance-x/examples.md` for sample audit reports
4. Customize `skills/kompliance-x/detection-criteria.md` if needed

## Need Help?

- Run `/help` in Claude Code
- Check [INSTALL.md](INSTALL.md) for troubleshooting
- Review [README.md](README.md) for detailed documentation

---

**Ready to ship compliant software!** 🚀
