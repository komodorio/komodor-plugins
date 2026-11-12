# Komodor plugins

Plugins that connect your coding agent to the Komodor agent platform MCP server. Once connected,
your agent can inspect, create, invoke and improve your agents. It finds the right guide on its
own through the server's `list_agentops_skills` and `load_agentops_skill` tools.

| Plugin | What it adds |
|---|---|
| `komodor-agents` | The `komodor` MCP server, signed in with your Komodor account (OAuth) |

## Claude Code

```bash
claude plugin marketplace add komodorio/komodor-plugins
claude plugin install komodor-agents@komodor
```

Then run `/mcp` in a session, pick `plugin:komodor-agents:komodor` and sign in.

The server URL defaults to `https://agentops.komodor.com/internal/mcp`. To use another one, pass it
at install or change it later with `/plugin configure komodor-agents@komodor`:

```bash
claude plugin install komodor-agents@komodor --config mcp_url=https://<your-host>/internal/mcp
```

## Codex

```bash
codex plugin marketplace add komodorio/komodor-plugins
codex plugin add komodor-agents@komodor
codex mcp login komodor
```

The plugin connects to `https://agentops.komodor.com/internal/mcp`. To use another one, add a
server with the same name; it takes precedence over the plugin's:

```bash
codex mcp add komodor --url https://<your-host>/internal/mcp
```

## Several workspaces

If your user belongs to more than one workspace, append `?account=<workspace-slug>` to the URL.
Without it you land in your oldest workspace. Ask your agent "which Komodor workspace am I in?"
to check; it calls `whoami`.

## Try it

Ask your agent: "improve my agent", "why did my agent's last run fail", or "create an agent that
triages Kubernetes alerts".

## License

[Apache-2.0](LICENSE)
