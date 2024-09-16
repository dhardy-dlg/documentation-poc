---
title: Code best practice and standard
---

# Code Best Practices and Standards
## Code Formatting
Proper code formatting improves readability, consistency, and maintainability across projects. The following are the key formatting guidelines:

### Language-Specific Guidelines
#### Python

Adhere to the PEP 8 standard.
Line length: 79 characters.
Indentation: 4 spaces per level.
Use snake_case for function and variable names.
Class names should use CamelCase.
Prefer single quotes for strings unless the string contains a single quote.
Place imports at the top of the file in the following order:
Standard library imports
Related third-party imports
Local application imports

#### JavaScript/TypeScript
Use Prettier for formatting.
Line length: 100 characters.
Indentation: 2 spaces per level.
Use camelCase for variables and functions.
Use PascalCase for classes and components.
Use const and let instead of var.
Always use semicolons.
Prefer single quotes for strings.

#### HTML/CSS

Indentation: 2 spaces.
Lowercase all tags and attribute names.
Close all tags (even self-closing tags).
Use double quotes for attribute values.
1.2. General Formatting Guidelines
Keep lines short and avoid horizontal scrolling.
Consistently apply comments for clarity:
Document all functions and classes with docstrings or block comments.
Use inline comments only for non-obvious logic.
Avoid trailing whitespace at the end of lines.
Organize code into logical sections and functions for readability.
## Pre-Commit Hooks
Pre-commit hooks are scripts that run automatically before you commit code to the repository, ensuring quality standards are met before code is checked in.

###  Setting Up Pre-Commit Hooks
Install pre-commit:

Ensure pre-commit is installed locally using pip or npm based on the technology stack:
```bash
pip install pre-commit
```
or
```bash
npm install pre-commit
```
Configuration: Create a .pre-commit-config.yaml file at the root of the repository with the following standard hooks:

Python:

```yaml
- repo: https://github.com/pre-commit/pre-commit-hooks
  rev: v4.0.0
  hooks:
    - id: trailing-whitespace
    - id: end-of-file-fixer
    - id: flake8
- repo: https://github.com/pre-commit/mirrors-black
  rev: v21.7b0
  hooks:
    - id: black
```
JavaScript/TypeScript:

```yaml
- repo: https://github.com/pre-commit/pre-commit-hooks
  rev: v4.0.0
  hooks:
    - id: trailing-whitespace
    - id: end-of-file-fixer
- repo: https://github.com/pre-commit/mirrors-eslint
  rev: v7.32.0
  hooks:
    - id: eslint
```

Running Pre-Commit:

To install hooks for the first time:
```bash
pre-commit install
```
To run pre-commit manually on all files:
```bash
pre-commit run --all-files
```
### Common Hooks to Include
Formatting:
Auto-format code (e.g., with black for Python, Prettier for JavaScript/TypeScript).
Linting:
Run linters (e.g., flake8 for Python, eslint for JavaScript).
Security:
Run security checks using tools like bandit for Python or npm audit for JavaScript.
Code Quality:
Enforce best practices with tools like pylint or eslint.
Testing:
Ensure that unit tests pass before allowing commits (pytest, jest).
3. Editor Configuration
To ensure consistency across all team members' local environments, configure the editor or IDE as follows:

## Recommended Editors/IDEs
Python: PyCharm, VS Code
JavaScript/TypeScript: VS Code, WebStorm
HTML/CSS: VS Code, Sublime Text
### General Configuration
Enable Auto-Formatting:

Configure the editor to auto-format on save using tools like black, Prettier, or custom settings.
Configure Indentation:

Ensure spaces are used for indentation (no tabs), and specify the appropriate number of spaces (e.g., 2 for JS, 4 for Python).
Linting Integration:

Enable integrated linters (e.g., flake8 for Python, eslint for JavaScript) to display warnings and errors as you code.
Trailing Whitespace and Newlines:

Configure the editor to trim trailing whitespace and insert a final newline at the end of files automatically.
###  VS Code Specific Settings
Add the following settings in your .vscode/settings.json file:

```json
{
  "editor.formatOnSave": true,
  "editor.trimAutoWhitespace": true,
  "files.insertFinalNewline": true,
  "python.linting.flake8Enabled": true,
  "python.linting.enabled": true,
  "prettier.singleQuote": true,
  "prettier.semi": true,
  "eslint.enable": true,
  "files.eol": "\n"
}
```
###  PyCharm Specific Settings
Auto-format on save:
Navigate to File > Settings > Tools > Actions on Save, and enable auto-formatting with black (for Python) or appropriate formatters.
Code style:
Go to File > Settings > Editor > Code Style, set indentation, and enable removal of trailing whitespace.
