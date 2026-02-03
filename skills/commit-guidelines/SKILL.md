---
name: git-auto-commit-analyst
description: Generates structured commit messages based on 'git diff --staged', focusing on technical accuracy, brevity, and automatic changelog category assignment. Use when generating commit messages or applying commit guidelines.
---

# Skill: Git Auto-Commit Analyst

## 1. Objective

Generate a structured commit message based on the contents of `git diff --staged`. The focus is on technical accuracy, conciseness, and automatic assignment of a changelog category.

## 2. Formatting Guidelines

Every output must strictly adhere to this structure:

- **Subject Line:** Maximum 50 characters, imperative mood (e.g., "Fix", "Add", "Update"), starting with a capital letter.
- **Description:** One blank line after the subject line. Describe the context (**why** was this done?) rather than the literal code change.
- **Trailer:** End immediately after the description with the appropriate `Changelog: <type>` tag.

## 3. Classification Logic

Analyze the staged files and determine the type based on the following definitions:

| Type             | Use Case                                                        |
| :--------------- | :-------------------------------------------------------------- |
| **added**        | New features, new components, or new files.                     |
| **fixed**        | Bug fixes, crash resolutions, or logic corrections.             |
| **changed**      | Changes to existing features that do not add new functionality. |
| **deprecated**   | Marking code to be removed in future versions.                  |
| **removed**      | Removal of old features or unused code.                         |
| **security**     | Vulnerability patches or authentication updates.                |
| **performance**  | Optimizations improving speed or memory usage.                  |
| **dependencies** | Dependency updates.                                             |
| **other**        | Refactoring, documentation, or build script changes.            |

---

## 4. Generation Instructions

When provided with a `git diff` or a list of changes:

1.  Scan the changes for core functionality.
2.  Draft the subject line and description.
3.  Select the most relevant changelog type.
4.  **Output only the commit message itself**, without extra explanation or Markdown code blocks (unless explicitly requested).

---

## 5. Example Output

Update user authentication timeout

Increased the session duration from 30 to 60 minutes to reduce
re-login frequency for active dashboard users.

Changelog: changed
