---
applyTo: '**'
---
# Applicability of these instructions
- These instructions apply only to some projects.
- Before starting to work on the projects, check which ones of the instructions apply to the project at hand.
- Document in the log file which instructions apply to the project.
- If unsure, ask me which instructions apply.
- For example, unit tests and integration tests do not apply to small projects, scripts or Jupyter Notebooks.

## Project Types and Applicable Instructions
When starting work, document in the log file which project type applies and which instruction sections are relevant:

**All Projects (Universal)**:
- Documentation and Output Format
- Keep a text file log and plan
- Use version control (basic)
- Code Organization
- Error Handling

**Small Projects/Scripts**:
- Universal instructions above
- Performance Considerations (if relevant)
- Security Best Practices (if handling external data)

**Jupyter Notebooks/Data Analysis**:
- Universal instructions above
- Using Jupyter Notebooks section
- Performance Considerations (for data processing)
- Skip: Build/Test Automation, Complex Git Workflow

**Medium to Large Projects**:
- All universal instructions
- Project Documentation (comprehensive README)
- Git Workflow Guidelines (branching, conventional commits)
- Build and Test Automation
- All Code Quality Standards
- Security Best Practices

**Production/Enterprise Projects**:
- All instructions apply
- Emphasis on comprehensive testing
- Strict security practices
- Full documentation requirements

## Log Template for Instruction Applicability
Copy this template to your log.md file when starting a project:

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

# General Coding Instructions

## Documentation and Output Format
**Applicability**: All Projects
- Do not use any images or even checkmarks in printouts or markdown files.
- When I ask for instructions for something, provide them in a markdown code block.
- Use clear, descriptive variable and function names that explain their purpose.
- Add comments to explain complex logic, algorithms, or non-obvious code sections.
- Keep documentation updated when making changes to functionality.


# Project Documentation and Planning

## Keep a text file log and plan
**Applicability**: All Projects
- Write all attempted changes and their results to the log file.
- Keep a summary of what changes are currently active.
- Keep a list of next steps to try.
- The subsections in the log file should be: failed changes, successful changes, next steps to try, and a summary of what changes are currently active.
- The log file should be in markdown format and use headings and subheadings to organize the information.
- The log file should be named `log.md` and be located in the root directory of the project.
- The log file should be updated before and after every change, whether it is successful or not.
- Before actually making the change, write down what you plan to do in the log file.
- After making the change, write down what you actually did and what the results were in the log file.
- If the change was successful, add it to the summary of what changes are currently active.
- If the change was not successful, add it to the list of failed changes.
- When starting from a work in progress state, write down the current state of the project in the log file before making any changes. Concentrate on the changes that have been made on top of the original project if such exists.

## Project Documentation
**Applicability**: Medium to Large Projects, Production Projects
- Maintain a comprehensive README.md that explains:
  - Project purpose and goals
  - Build and installation instructions
  - Usage examples
  - Architecture overview
  - Contributing guidelines
- Update documentation when adding new features or changing existing functionality.
- Use consistent markdown formatting across all documentation files.

# Version Control Best Practices

## Use version control
**Applicability**: All Projects
- Use git for version control always.
- Commit the changes only when prompted to do so.
- Write meaningful commit messages that describe what changes were made and why, but do not overdo it.
- Make sure that the commit messages describe a meaningful story of how the changes have progressed.
- Use branches for different features or experiments.
- Merge branches only when prompted to do so.
- Push changes to the remote repository only when prompted to do so.
- Pull changes from the remote repository only when prompted to do so.
- Use stashing for reverting unsuccessful changes.

## Git Workflow Guidelines
**Applicability**: Medium to Large Projects, Production Projects
- Create feature branches with descriptive names (e.g., `feature/fsr4-optimization`, `fix/memory-leak`).
- Keep commits atomic - each commit should represent a single logical change.
- Use conventional commit messages when appropriate:
  - `feat:` for new features
  - `fix:` for bug fixes
  - `docs:` for documentation changes
  - `refactor:` for code refactoring
  - `test:` for adding or modifying tests
- Review changes before committing using `git diff` or `git status`.
- Use `.gitignore` to exclude build artifacts, temporary files, and sensitive data.

# Build and Test Automation

## Create a build script and test script
**Applicability**: Medium to Large Projects, Production Projects
- Create a build script that automates the build process of the project.
- The build script should be named `build.sh` and be located in the root directory of the project.
- The build script should be executable and use bash as the shell.
- Write the build procedure to the log file under a separate heading.
- Always use the build script to build the project, never build manually.
- Create a test script that automates the testing process of the project.
- The test script should be named `test.sh` and be located in the root directory of the project.
- The test script should be executable and use bash as the shell.

## Build Script Requirements
**Applicability**: Medium to Large Projects, Production Projects
- Include error handling with `set -e` to exit on first error.
- Include verbose output with `set -x` for debugging when needed.
- Check for required dependencies and provide clear error messages if missing.
- Support different build configurations (debug, release, etc.) through command-line arguments.
- Clean previous builds when appropriate to ensure reproducible builds.
- Validate the build output and report success/failure clearly.

## Testing Guidelines
**Applicability**: Medium to Large Projects, Production Projects
- Write unit tests for new functionality.
- Include integration tests for complex features.
- Test script should run all tests and provide clear pass/fail reporting.
- Include performance benchmarks where relevant.
- Test on different configurations and environments when possible.

# Code Quality Standards

## Code Organization
**Applicability**: All Projects
- Follow consistent file and directory naming conventions.
- Group related functionality into modules or namespaces.
- Keep functions and classes focused on a single responsibility.
- Use meaningful directory structures that reflect the project architecture.

## Error Handling
**Applicability**: All Projects
- Always handle potential error conditions.
- Provide informative error messages that help with debugging.
- Use appropriate logging levels (debug, info, warning, error).
- Don't silently ignore errors - either handle them properly or let them propagate.

## Performance Considerations
**Applicability**: All Projects (when relevant)
- Profile code before optimizing to identify actual bottlenecks.
- Document performance-critical sections.
- Consider memory usage and avoid unnecessary allocations.
- Use appropriate data structures for the task at hand.

## Security Best Practices
**Applicability**: All Projects (when handling external data or in production)
- Validate all input data.
- Avoid hardcoded credentials or sensitive information.
- Use secure coding practices appropriate for the language and domain.
- Keep dependencies updated to avoid known vulnerabilities.

## File Access Outside Workspace
**Applicability**: All Projects (when explicitly permitted)
- **NEVER access files outside the workspace without explicit permission**.
- **Permission Requirements**:
  - **Read Permission**: Must be explicitly granted with specific file paths
  - **Write Permission**: Must be explicitly granted separately from read permission
  - **Default**: No access to files outside workspace
- **Permission Validation**:
  - If only read permission is given, you are **FORBIDDEN** to modify the file
  - If write permission is not explicitly granted, treat as read-only
  - Always confirm permission scope before any file operation
- **VSCode Integration**:
  - When given permission to access a file, open it in the VSCode editor
  - Use VSCode's file editing tools for reading and writing
  - This makes the file more accessible and visible during work
- **Documentation Requirements**:
  - Document all external file access in the project log
  - Record the permission level granted (read-only vs read-write)
  - Note the purpose and outcome of external file operations
- **Safety Guidelines**:
  - Always use absolute paths when accessing external files
  - Verify file exists before attempting access
  - Handle file access errors gracefully
  - Never assume file permissions or modify without explicit write permission

# Using Jupyter Notebooks
**Applicability**: Jupyter Notebooks/Data Analysis Projects
- Jupyter notebooks should have all the import statements in the first cell.
- After the import statements, include the definitions of all the helper functions that are needed in the notebook. These are either defined in the cell, or they are imported from the separate python file or files. First try to include them in the cell, if that becomes too large, move them to a separate python file and import from there.
- Use markdown cells to provide context, explanations, and instructions for each section of the notebook.
- Do not use the Jupyter Notebook to document the failed changes etc. For example, Jupyter notebook should not contain a note about "Fixing the bug that caused the wrong results in cell 5". Such notes should go to the log file instead.
- If we are comparing different approaches, the different approaches should be in separate cells of the notebook and should follow each other as identically as possible.
Finally, if comparing different appproaches, the results should be compared in a separate cell at the end of the notebook.
- Use tests should be as minimal as possible, concentrating on the main functionality.
- Do not create additional debug cells without explicit permission.
- Never use on ASCII characters in printouts. Use only text and numbers. Ask to remove characters that are not normal text or numbers.