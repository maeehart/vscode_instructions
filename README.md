# VSCode Instructions

A comprehensive set of coding instructions and best practices for software development projects, designed to be used with AI assistants and development teams.

## Overview

This repository contains structured coding instructions that help ensure consistent, high-quality development practices across different types of projects. The instructions include applicability guidelines to help determine which practices apply to specific project types.

## Contents

- `general_coding_instructions.md` - Complete set of coding instructions with applicability guidelines
- `VSCODE_SETUP.md` - Detailed guide for integrating these instructions with VSCode
- `log_template.md` - Template for project development logs

## Project Types Covered

The instructions are designed to work with different project types:

- **All Projects (Universal)** - Core practices that apply everywhere
- **Small Projects/Scripts** - Minimal set for simple work
- **Jupyter Notebooks/Data Analysis** - Specialized for data work  
- **Medium to Large Projects** - Full professional development practices
- **Production/Enterprise Projects** - Maximum rigor and security

## Key Features

### Applicability System
Each instruction section includes clear applicability markers showing which project types it applies to:
- Clear project type classifications
- Section-by-section applicability markers
- Ready-to-use log template for documenting instruction usage

### Comprehensive Coverage
- Documentation and output formatting
- Project planning and logging
- Version control best practices
- Build and test automation
- Code quality standards
- Security best practices
- Jupyter notebook guidelines

## Usage

### For AI Assistants
1. Reference these instructions when starting new projects
2. Determine project type and applicable instruction sections
3. Use the provided log template to document which instructions apply
4. Follow the relevant guidelines throughout development

### For Development Teams
1. Adopt instructions appropriate for your project type
2. Customize sections as needed for your specific requirements
3. Use as a checklist for code reviews and project setup
4. Reference for establishing team coding standards

## Getting Started

## Quick VSCode Setup

**For immediate use with VSCode and AI assistants:**

1. **Clone this repository**:
   ```bash
   cd ~/dev
   git clone https://github.com/maeehart/vscode_instructions.git
   ```

2. **Add to VSCode settings** (`settings.json`):
   ```json
   {
     "copilot.context.additionalFiles": [
       "~/dev/vscode_instructions/*.md",
       ".github/instructions/*.md"
     ]
   }
   ```

3. **In your project**, create a reference:
   ```bash
   mkdir -p .github/instructions
   ln -s ~/dev/vscode_instructions/general_coding_instructions.md .github/instructions/
   ```

4. **Copy log template**:
   ```bash
   cp ~/dev/vscode_instructions/log_template.md ./log.md
   ```

**📖 For detailed setup instructions, see [VSCODE_SETUP.md](VSCODE_SETUP.md)**

### Initial Project Setup

### Initial Project Setup

When starting a new project with these instructions:

1. **Assess Project Type**: Determine which category your project falls into
2. **Set Up Instructions**: Choose one of the VSCode integration methods above
3. **Create Log File**: Set up `log.md` for tracking changes and progress
4. **Document Applicability**: Use the log template to check applicable instructions
5. **Configure VSCode**: Ensure your editor can access and reference the instructions
6. **Follow Guidelines**: Apply relevant instructions throughout development

### VSCode Workflow Integration

#### For AI Assistant Users:
1. **Reference instructions** in your prompts: "Please follow the coding instructions in `.github/instructions/general_coding_instructions.md`"
2. **Context inclusion**: Ensure your AI assistant can access the instructions file
3. **Regular reviews**: Periodically check that generated code follows the applicable guidelines

#### For Manual Development:
1. **Use as checklist**: Review relevant sections before starting new features
2. **Code review reference**: Check against applicable guidelines during reviews
3. **Team alignment**: Ensure all team members are familiar with applicable instructions

#### Recommended VSCode Extensions:
- **Markdown All in One**: For editing instruction files
- **GitLens**: For following version control best practices
- **Todo Tree**: For tracking todos in log files
- **Bracket Pair Colorizer**: For code organization
- **Error Lens**: For immediate error feedback

### Log Template

Copy this template to your project's `log.md` file:

```markdown
## Applicable Instructions Assessment
- **Project Type**: [Small Script/Jupyter Notebook/Medium Project/Large Project/Production]
- **Instructions Applied**: 
  - [ ] Documentation and Output Format
  - [ ] Keep a text file log and plan
  - [ ] Use version control (basic)
  - [ ] Git Workflow Guidelines (for medium+ projects)
  - [ ] Build and Test Automation (for medium+ projects)  
  - [ ] Project Documentation (comprehensive for medium+ projects)
  - [ ] Code Organization
  - [ ] Error Handling
  - [ ] Performance Considerations
  - [ ] Security Best Practices
  - [ ] Using Jupyter Notebooks (if applicable)
- **Instructions Skipped**: [List with reasoning]
```

## Examples

### Small Script Project
For a simple utility script, you would typically apply:
- Documentation and Output Format
- Keep a text file log and plan
- Use version control (basic)
- Code Organization
- Error Handling

### Large Software Project
For a comprehensive application, you would apply all sections including:
- All universal instructions
- Git Workflow Guidelines
- Build and Test Automation
- Project Documentation
- All Code Quality Standards
- Security Best Practices

## Contributing

Feel free to suggest improvements or additions to these instructions. When contributing:

1. Follow the existing structure and format
2. Include clear applicability guidelines for new sections
3. Update the log template if adding new instruction categories
4. Provide examples where helpful

## License

These instructions are provided as-is for use in software development projects.