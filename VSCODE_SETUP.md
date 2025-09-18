# VSCode Setup Guide

This guide explains how to integrate the coding instructions with Visual Studio Code for optimal development workflow.

## Quick Setup (Recommended)

### 1. Clone and Reference
```bash
# Clone instructions to central location
cd ~/dev
git clone https://github.com/maeehart/vscode_instructions.git

# In your project directory
mkdir -p .github/instructions
ln -s ~/dev/vscode_instructions/general_coding_instructions.md .github/instructions/
```

### 2. Configure VSCode Settings
Add to your global VSCode settings (Ctrl/Cmd + Shift + P → "Preferences: Open Settings (JSON)"):

```json
{
  "files.associations": {
    "*.instructions.md": "markdown"
  },
  "copilot.context.additionalFiles": [
    ".github/instructions/*.md",
    "~/dev/vscode_instructions/*.md"
  ],
  "markdown.preview.breaks": true,
  "markdown.preview.linkify": true
}
```

## Project-Specific Setup

### For Each New Project

1. **Create instruction reference**:
   ```bash
   mkdir -p .github/instructions
   echo "# Project Instructions\n\nThis project follows: ~/dev/vscode_instructions/general_coding_instructions.md" > .github/instructions/README.md
   ```

2. **Set up workspace settings** (`.vscode/settings.json`):
   ```json
   {
     "copilot.context.additionalFiles": [
       ".github/instructions/*.md"
     ],
     "files.watcherExclude": {
       "**/log.md": false
     }
   }
   ```

3. **Create initial log file**:
   ```bash
   cp ~/dev/vscode_instructions/log_template.md ./log.md
   ```

## AI Assistant Integration

### GitHub Copilot
1. **Context inclusion**: The settings above automatically include instruction files in Copilot's context
2. **Prompt enhancement**: Reference instructions in your prompts:
   ```
   "Please implement this feature following the coding instructions in .github/instructions/"
   ```

### Other AI Assistants
1. **File referencing**: Always include the instruction file path in your prompts
2. **Context management**: Ensure the assistant can access the instruction files
3. **Regular reminders**: Periodically remind the assistant about applicable instruction sections

## VSCode Extensions for Instruction Following

### Essential Extensions
- **Markdown All in One** (`yzhang.markdown-all-in-one`)
  - Edit and preview instruction files
  - Navigate between instruction sections

- **GitLens** (`eamodio.gitlens`)
  - Follow version control best practices
  - Track changes according to instructions

- **Todo Tree** (`gruntfuggly.todo-tree`)
  - Track todos in log files
  - Configure for log.md format:
    ```json
    "todo-tree.general.tags": [
      "TODO",
      "FIXME", 
      "Failed",
      "Successful",
      "Next Steps"
    ]
    ```

### Code Quality Extensions
- **Error Lens** (`usernamehw.errorlens`)
  - Immediate error feedback (Error Handling instructions)

- **Bracket Pair Colorizer** (`coenraads.bracket-pair-colorizer-2`)
  - Better code organization visualization

- **Prettier** (`esbenp.prettier-vscode`)
  - Consistent code formatting

## Workflow Templates

### Starting a New Feature
1. **Check log.md** for current project state
2. **Update log.md** with planned changes
3. **Reference instructions** for applicable guidelines
4. **Implement following** relevant instruction sections
5. **Update log.md** with results

### Code Review Checklist
Use this VSCode snippet (File → Preferences → Configure User Snippets → markdown):

```json
{
  "Instruction Review": {
    "prefix": "review-instructions",
    "body": [
      "## Code Review - Instruction Compliance",
      "",
      "### Applicable Instructions Followed:",
      "- [ ] Documentation and Output Format",
      "- [ ] Code Organization", 
      "- [ ] Error Handling",
      "- [ ] Performance Considerations",
      "- [ ] Security Best Practices",
      "",
      "### Notes:",
      "- ",
      "",
      "### Action Items:",
      "- "
    ]
  }
}
```

## Troubleshooting

### Instructions Not Loading in AI Context
1. Check file paths in VSCode settings
2. Verify instruction files are readable
3. Restart VSCode and AI extension
4. Use absolute paths if relative paths fail

### Log File Not Updating
1. Ensure `log.md` is not in `.gitignore`
2. Check file permissions
3. Verify VSCode can write to project directory

### Extension Conflicts
1. Disable conflicting markdown extensions temporarily
2. Check extension compatibility
3. Update VSCode and extensions to latest versions

## Advanced Configuration

### Multi-Project Workspace
For VSCode workspaces with multiple projects:

```json
{
  "folders": [
    {
      "name": "Project 1",
      "path": "./project1"
    },
    {
      "name": "Project 2", 
      "path": "./project2"
    }
  ],
  "settings": {
    "copilot.context.additionalFiles": [
      "~/dev/vscode_instructions/*.md",
      "*/.github/instructions/*.md"
    ]
  }
}
```

### Custom Instruction Categories
Create project-specific instruction files:

```bash
# In .github/instructions/
cp ~/dev/vscode_instructions/general_coding_instructions.md ./project_specific_instructions.md
# Edit to add project-specific sections
```

## Getting Help

- **Issues**: Report problems at https://github.com/maeehart/vscode_instructions/issues  
- **Discussions**: Ask questions in repository discussions
- **Updates**: Watch the repository for instruction updates