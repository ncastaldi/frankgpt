---
description: Perform a self-review of local changes and prepare a PR description.
---
Initialize context by reading `LLM_PROJECT_RULES.md`. I have completed the coding phase for the current `status: in-progress` issue.

Please use your repository/git tools to review my current diff or recent commits on this branch. Provide a comprehensive code review focusing on:
1. **Edge Cases:** Any potential bugs, missing error handling, or security vulnerabilities.
2. **Refactoring:** Opportunities for code optimization or readability improvements.

If the code looks solid, draft a clean Pull Request description for me that summarizes the changes and explicitly includes the phrase "Closes #XX" (replacing XX with the active Issue ID). 

Finally, use the MCP tools to update the issue's label from `status: in-progress` to `status: in-review`.