---
applyTo: '**'
---
### Coding standards, domain knowledge, and preferences that AI should follow.

# Objective
- Deliver high-quality, modular, maintainable code across all languages
- Prioritize modularity, cross-platform compatibility, functionality, industry standards

# Core Principles
- Modularity: Organize code into reusable, self-contained modules with clear interfaces
- Compatibility: Ensure code runs on Windows, macOS, Linux using platform-neutral libraries (e.g., `pathlib` in Python, `path` in Node.js)
- Functionality: Prioritize robust, reliable code over speed or aesthetics
- Industry Standards: Use camelCase (JavaScript), snake_case (Python), descriptive naming
- Iterative Improvement: Suggest 2nd, 3rd, 4th-order enhancements within request scope

# General Guidelines
- Abstraction: Interpret requests as a professional programmer, focusing on intent and best practices
- Clarifications: For files >100 lines, include inline questions and await response
- Conciseness: Provide concise, comprehensive responses
- Path Handling:
  - Use relative paths in code for portability
  - Log absolute paths for debugging (DEBUG level)
  - Use platform-neutral path utilities (e.g., `pathlib`)
  - Robust error handling for path operations with descriptive messages
- Error Logging:
  - Use `Logger.py` (Python) or equivalents (e.g., `winston` for Node.js)
  - Log levels: DEBUG (cyan), INFO (cyan), WARNING (yellow), ERROR (red), SUCCESS (green) with ANSI colors
  - Include Nerd Font glyphs in console output (e.g., `✔` for SUCCESS, `✗` for ERROR)
- Variable Usage:
  - Avoid TypeScript types unless requested
  - Remove unused variables; use `// @ts-ignore` for TypeScript warnings
- Naming Conventions:
  - Use camelCase (JavaScript), snake_case (Python), language-appropriate conventions
  - Descriptive names (e.g., `process_user_data` not `process`)
- Font Preferences:
  - Use Nerd Fonts for console output (`✔`, `✗`, `ℹ`) and editor configs
  - Avoid light themes in UI/editor
- Iterative Suggestions:
  - 2nd order: Immediate improvements (e.g., modular utilities)
  - 3rd order: Optimizations/alternative architectures (e.g., config-driven logging)
  - 4th order: Scalability/maintainability (e.g., plugin systems)

# Specific Inclusions
- Error Handling:
  - Wrap path operations in try-catch with descriptive messages (e.g., `✗ Could not locate file at <absolute_path>`)
- Logging:
  - Use `Logger.py` for Python; equivalents for other languages
  - Log absolute paths for debugging
  - Colors: red (`\033[31m`), yellow (`\033[33m`), green (`\033[32m`), cyan (`\033[36m`)
  - Nerd Font glyphs in console
- Path Utilities:
  - Reusable path functions (e.g., `get_relative_path`, `resolve_absolute_path`) using `pathlib` or equivalent
- Package Management:
  - Include `requirements.txt` for Python with pip commands
  - Log download confirmation (e.g., `Successfully installed package X`)
  - Warn for packages >500MB (e.g., `⚠ Package X is 750MB. Confirm?`)
- Code Documentation:
  - Brief purpose description at file top
  - Clear, concise comments for complex logic

# Specific Exclusions
- Unstable Code: Avoid experimental, unverified, or amateur code
- Absolute Paths in Code: Use relative paths; absolute paths for debug logs only
- Sacrificing Functionality: Prioritize function over speed/aesthetics
- Disproportionate Layouts: Ensure readable code formatting
- Light Themes: Use dark themes for UI/editor
- Unnecessary Escaping: Minimize characters needing escaping

# Output Styling
- Console Output:
  - Errors: Red (`\033[31m`, `✗`)
  - Warnings: Yellow (`\033[33m`, `⚠`)
  - Success: Green (`\033[32m`, `✔`)
  - Info/Debug: Cyan (`\033[36m`, `ℹ`)
- Code Completeness:
  - Output complete code without truncation
  - For code >25,000 characters, check for hidden characters/symbols
- Logging Wrapper:
  - Use `Logger.py` for Python with timestamped, contextual logs

# Preferences
- Platform Neutrality:
  - Use cross-platform languages (e.g., Python, JavaScript) and formats (e.g., JSON)
  - Prefer `pathlib` (Python), `path` (Node.js) for paths
- Quick Questions:
  - Switch to short, conversational teaching context for `quick question` prefix
  - Revert to execution context after one response
- Debugging:
  - Always log absolute paths for file operations (DEBUG level)
  - Example: `ℹ DEBUG: Resolved ./config.json to /home/user/project/config.json`

# Implementation Notes
- Logger.py: Enhanced with error handling, Nerd Font glyphs, absolute path logging
- Error Handling Example (Python):
  ```python
  try:
      with open("config.json", "r") as file:
          data = json.load(file)
  except FileNotFoundError:
      logger.error("✗ Could not locate config.json at /home/user/project/config.json")
      raise
  ```
- Logging Example (Python):
  ```python
  logger.debug("ℹ Starting initialization")
  logger.success("✔ Application started")
  logger.warning("⚠ Deprecated function used")
  logger.error("✗ Database connection failed")
  ```

# Iterative Improvement Suggestions
- 2nd Order: Modularize `Logger.py` into configuration/formatting classes
- 3rd Order: Add JSON config for log levels/output destinations
- 4th Order: Implement plugin system for custom log handlers (e.g., network logging)
