## Plan: FrankGPT MCP Server MVP

Build a Python MCP server that exposes FrankGPT core commands as structured tools, reusing the v6 instruction modules as prompt assets. Start with four core tools (/quickstart, /create, /review, /help), stdio transport, and Claude Desktop compatibility, then validate with integration tests and sample sessions.

**Steps**
1. Phase 1 - Scaffold and runtime setup. Create a new Python package for the MCP server (Poetry or uv), configure stdio transport, logging, and environment-driven settings. Add a thin server entrypoint that registers tools from a registry.
2. Phase 1 - Prompt asset loader. Implement a loader that reads v6 markdown instruction assets (core + selected skills) and composes deterministic system context for each tool invocation. Include caching and file-change-safe reload behavior for local development.
3. Phase 2 - Tool contract design. Define Pydantic models for each MVP tool input/output with strict validation and user-friendly error surfaces. Keep schemas intentionally minimal for v1.
4. Phase 2 - Core tool implementation. Implement quickstart/create/review/help handlers as workflow wrappers that call a model backend with composed context from Step 2. Depends on Steps 1-3.
5. Phase 2 - Model backend abstraction. Add provider interface and first implementation (OpenAI-compatible or Anthropic-compatible) so tools are provider-agnostic. Depends on Step 1 and parallel with Step 4 once contracts are stable.
6. Phase 3 - MCP integration hardening. Add robust tool registration metadata, timeout handling, structured exceptions, and safe fallback messages when provider/config is missing. Depends on Steps 4-5.
7. Phase 3 - Client integration docs. Add Claude Desktop MCP config examples and local run instructions, plus troubleshooting notes for missing env vars and tool discovery. Depends on Step 6.
8. Phase 4 - Verification and release readiness. Add unit tests for schema validation and loader behavior, plus integration tests for tool execution and server startup. Run lint/type/test gates before handoff. Depends on Steps 1-7.

**Relevant files**
- .github/copilot-instructions.md - Existing project instruction entrypoint; add section describing MCP server usage and limits.
- v6/Frank.core.agent.md - Canonical core behavior and command definitions for tool semantics.
- v6/skills/style.craft.instructions.md - Workflow style constraints for create/review style outputs.
- v6/skills/style.markdown.instructions.md - Output formatting constraints used by core tools.
- v6/copilot-instructions.md - Add runtime integration notes and compatibility statement.
- README.md - Add top-level "Run as MCP server" path and links.
- New package at repo root for Python MCP runtime (server entrypoint, config, loader, tools, tests).

**Verification**
1. Start server locally via module entrypoint and confirm MCP handshake succeeds in a compatible client.
2. Validate each MVP tool with one happy-path and one invalid-input case, confirming schema errors are explicit.
3. Run automated tests (unit + integration) and ensure all pass in CI-equivalent environment.
4. Perform manual Claude Desktop check: tools are discovered, callable, and return deterministic markdown/JSON output shape.
5. Confirm instruction loader picks up v6 content and that cache invalidation works after editing source markdown.

**Decisions**
- Runtime selected: Python.
- Initial scope selected: MVP core tools only (/quickstart, /create, /review, /help).
- Transport selected: stdio-first for Claude Desktop and similar MCP clients.
- Included now: tool schemas, loader, provider abstraction, docs, tests.
- Excluded now: specialty tools, remote transport, auth proxying, persistent datastore, multi-tenant routing.

**Further Considerations**
1. Model provider baseline for MVP: Anthropic SDK path or OpenAI-compatible path; recommendation is OpenAI-compatible abstraction first if multi-provider portability is desired.
2. Packaging choice: Poetry (matches reference repo style) vs uv/pip-tools; recommendation is Poetry for parity with your authentik-mcp workflow.
3. Specialty expansion strategy after MVP: ITIL first as Phase 2 extension due to clear command contracts and high operational value.