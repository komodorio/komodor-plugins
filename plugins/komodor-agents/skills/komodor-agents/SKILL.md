---
name: komodor-agents
description: Load this first, before any komodor MCP tool call and before asking the user anything, whenever a request concerns their agents or the Komodor agent platform (also called AgentOps or KAOP) - for example "improve my agent", "why did my agent fail", "create an agent". Covers creating, deploying, invoking, debugging, evaluating and improving agents, and their runs, workflows, automations, guardrails, budgets, credentials, MCP gateway, knowledge base, memory and Slack channels. It says which komodor MCP guide to load for the task.
---

# Komodor agent platform

The `komodor` MCP server carries a usage guide for every domain it covers. The tool descriptions
alone leave out the argument shapes, resource kinds and pitfalls, so read the guide first.

1. Call `list_agentops_skills` with `query` set to the task in your own words, for example
   `"improve an agent's quality"`.
2. Call `load_agentops_skill` with the best match's `name`, and follow it.
3. Only then call the tools it names. Load another guide when the task moves to a new domain.

If neither tool is available, the MCP server is not connected or not signed in. Tell the user to
run `/mcp` (Claude Code) or `codex mcp login komodor` (Codex), and see this plugin's README for the
server URL.

Call `whoami` when the user asks which workspace you are in. Switching workspace means connecting
to a different URL (`?account=<workspace-slug>`), not a tool call.
