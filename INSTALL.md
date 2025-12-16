# Installation Guide

## Quick Install

### Option 1: Project-Specific Installation (Recommended)

Install this skill for a specific project:

```bash
# Navigate to your project
cd /path/to/your/project

# Copy the .claude directory from this repo
cp -r /path/to/compliance-agent/.claude .

# The skill is now available in this project!
```

### Option 2: Global Installation

Install this skill for all your projects:

```bash
# Create personal skills directory if it doesn't exist
mkdir -p ~/.claude/skills

# Copy the compliance-audit skill
cp -r /path/to/compliance-agent/.claude/skills/compliance-audit ~/.claude/skills/

# The skill is now available in all your projects!
```

## Verification

After installation, verify the skill is working:

1. Open Claude Code in your project (or any project if you did global install)
2. Ask: "What skills are available?"
3. You should see "compliance-audit" in the list

Or test it directly:
```
"Can you audit my project for compliance?"
```

Claude should respond by analyzing your project and asking questions about applicable frameworks.

## Manual Installation

If you prefer to set up manually:

1. **Create the skill directory structure:**
   ```bash
   mkdir -p .claude/skills/compliance-audit/{reference,templates}
   ```

2. **Copy the files:**
   - SKILL.md → .claude/skills/compliance-audit/
   - detection-criteria.md → .claude/skills/compliance-audit/
   - examples.md → .claude/skills/compliance-audit/
   - All reference/*.md files → .claude/skills/compliance-audit/reference/
   - All templates/*.md files → .claude/skills/compliance-audit/templates/

3. **Verify the structure:**
   ```
   .claude/skills/compliance-audit/
   ├── SKILL.md
   ├── detection-criteria.md
   ├── examples.md
   ├── reference/
   │   ├── gdpr.md
   │   ├── hipaa.md
   │   ├── pci-dss.md
   │   ├── ccpa.md
   │   └── soc2.md
   └── templates/
       ├── executive-summary.md
       └── detailed-report.md
   ```

## Updating

To update the skill:

1. Pull the latest changes from this repo
2. Re-run the installation command for your chosen option
3. The skill will be updated with new framework requirements and improvements

## Uninstalling

### Project-Specific
```bash
rm -rf .claude/skills/compliance-audit
```

### Global
```bash
rm -rf ~/.claude/skills/compliance-audit
```

## Troubleshooting

### Skill Not Appearing

**Problem:** Claude doesn't recognize the skill

**Solutions:**
1. Verify the .claude/skills/compliance-audit directory exists
2. Check that SKILL.md has proper YAML frontmatter
3. Restart Claude Code session
4. Try asking directly: "Can you audit for GDPR compliance?"

### Wrong Framework Detection

**Problem:** Claude suggests frameworks that don't apply

**Solution:**
- Answer "no" to confirmation questions
- The skill asks before auditing each framework
- Edit detection-criteria.md to adjust detection logic

### Missing Dependencies

**Problem:** Skill references files that don't exist

**Solution:**
1. Verify all files copied correctly
2. Check file permissions: `ls -la .claude/skills/compliance-audit`
3. Ensure all reference/*.md files are present

## Requirements

- Claude Code CLI installed
- Git (for cloning this repo)
- Basic command-line knowledge

## Next Steps

After installation:
1. Read README.md for usage examples
2. Try an audit on a test project first
3. Review examples.md to see sample outputs
4. Customize detection-criteria.md if needed for your use case

## Support

- Check README.md for general documentation
- Review examples.md for sample audit reports
- Consult detection-criteria.md for framework detection logic
- Report issues or contribute improvements via GitHub

---

Happy auditing! 🔒
