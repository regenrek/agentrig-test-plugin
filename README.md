# Test Submission

Reference plugin used to exercise the AgentRig registry submission and review
pipeline. It is intentionally minimal but covers every artifact kind that a
plugin can bundle:

- two skills under `skills/`
- one MCP server config at `.mcp.json`
- one hook config at `hooks/hooks.json`

This repo doubles as the upstream source for the standalone fixture artifacts
that the registry hosts under `skills/regenrek/test-skill/`,
`mcps/regenrek/test-mcp/`, and `hooks/regenrek/test-hook/`.

## Layout

```
.plugin/
  plugin.json          # Plugin manifest
skills/
  test-submission/     # Bundled skill 1
    SKILL.md
  checklist-runner/    # Bundled skill 2
    SKILL.md
    scripts/run.sh
.mcp.json              # Bundled MCP server config
hooks/
  hooks.json           # Bundled hook config
README.md
LICENSE
```

## Local testing

```bash
agentrig plugin bundle .
agentrig plugin install codex agentrig/regenrek.test-submission@0.2.0
```

Standalone artifacts can be installed independently from the registry:

```bash
agentrig skill install codex agentrig/regenrek.test-skill@0.1.0
agentrig mcp   install codex agentrig/regenrek.test-mcp@0.1.0
agentrig hook  install codex agentrig/regenrek.test-hook@0.1.0
```

## License

MIT (c) 2026 regenrek
