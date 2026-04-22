# Test Submission

Tiny sample plugin used to smoke-test the agentrig submission review pipeline.

## Publishing

This scaffold is for authoring and local testing. Publish it to a static signed
registry before using the public install command.

## Local testing

```bash
agentrig plugin bundle .
cd ..
agentrig plugin export --agent claude --pluginsDir ./regenrek.test-submission --out dist/claude-marketplace
```

After publishing, install it with the canonical registry ref:

```bash
agentrig registry add your-registry https://example.com/agentrig
agentrig plugin install codex your-registry/regenrek.test-submission@0.1.0
```

## Usage

After installation, the provider plugin will expose this plugin's skills, commands, agents, and related assets in the target environment.

## Structure

```
regenrek.test-submission/
├── .plugin/
│   └── plugin.json     # Plugin manifest
├── skills/             # Skills directory
│   └── test-submission/  # Main skill
│       └── SKILL.md    # Skill instructions
├── agents/             # Subagents (optional)
├── hooks/              # Hooks (optional)
│   └── hooks.json
├── rules/              # Rule files (optional)
├── .mcp.json           # MCP servers (optional)
├── .lsp.json           # LSP servers (optional)
└── CHANGELOG.md        # Plugin changelog
```

## Development

### Refresh plugin metadata

Update `.plugin/plugin.json` when plugin identity or public metadata changes.

### Export for Claude Marketplace

```bash
cd ..
agentrig plugin export --agent claude --pluginsDir ./regenrek.test-submission --out dist/claude-marketplace
```

## License

MIT © 2026 regenrek
