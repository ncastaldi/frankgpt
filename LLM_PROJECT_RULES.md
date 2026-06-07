# 🤖 LLM Project Management Instructions

> **Notice to the AI Assistant:** This repository uses a simulated Kanban project board driven entirely by **GitHub Issues, Labels, and Milestones** via standard GitHub MCP tools. Read this document to understand the workflow rules before creating, updating, or listing tasks.

---

## 🏷️ 1. Kanban Board Columns (Labels)
We use `status:` labels to act as our Kanban columns. When "moving" a task across the board, **always remove the old status label** and apply the new one. 

*   `status: backlog` — Ideas, long-term roadmaps, or unprioritized bugs.
*   `status: todo` — Selected for immediate next steps.
*   `status: in-progress` — What I am actively working on right now.
*   `status: blocked` — Stuck waiting on something else.
*   `status: in-review` — Code written, waiting for self-review or PR merge.
*   `status: done` — Fully completed. *(Note: Issues with this label should also be Closed).*

### Optional Metadata Labels
*   **Priority:** `priority: high`, `priority: medium`, `priority: low`
*   **Type:** `type: feature`, `type: bug`, `type: refactor`, `type: chore`

---

## 🗓️ 2. Milestones (Sprints / Epics)
*   Group issues into **Milestones** for major feature sets or time-boxed sprints (e.g., `v1.0-mvp`, `Sprint 3`).
*   Always check for an existing milestone before assigning it. If a requested milestone doesn't exist, create it.

---

## 🛠️ 3. AI Execution Protocols

### Protocol A: Generating the "Board View"
When asked to "show the board," "give a status update," or asked "what's next?", you must:
1. List or search all open issues in the repository.
2. Group the discovered issues by their `status:` label.
3. Print a clean, text-based Kanban overview for the user. 
4. Highlight any items marked `priority: high` or `status: blocked`.

### Protocol B: Task Creation
When the user asks you to create a task or log a bug:
1. Write a clear, concise issue title and a markdown description (with acceptance criteria if applicable).
2. Apply `status: todo` (or `status: backlog` if specified).
3. Apply relevant priority and type labels based on the context of the conversation.

### Protocol C: Moving Tasks
When the user says a task is active, done, or blocked:
1. Find the target issue.
2. Strip the old `status:` label.
3. Apply the new accurate `status:` label.
4. If the new status is `status: done`, close the issue.

---

## 📝 4. Quick-Start Prompts for the User
*   *"Read LLM_PROJECT_RULES.md and print out our current Kanban board overview."*
*   *"Based on our conversation about the database migration bug, create a new high-priority issue for it."*
*   *"I just finished implementing the auth middleware. Update its issue to 'done' and show me what's left in my 'todo' column."*