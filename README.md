# Claude Marketplace

Personal Claude Code plugin marketplace with skills and tools.

## Plugins

| Plugin | Description |
|--------|-------------|
| `claude-code` | Permissions config, marketplace management |
| `diagrams` | ASCII and Mermaid diagram creation |
| `effect` | Effect framework patterns |
| `github-workflows` | PR feedback processing |
| `kitz` | Testing patterns |
| `library-adt` | ADT conventions |
| `library-standards` | Library structure conventions |
| `react` | React component patterns |
| `typescript` | TypeScript conventions |
| `zed` | Zed editor config |

## Installation

### For Projects (Team Use)

Add to your project's `.claude/settings.json`:

```json
{
  "extraKnownMarketplaces": {
    "jasonkuhrt": {
      "source": {
        "source": "github",
        "repo": "jasonkuhrt/claude-marketplace"
      }
    }
  },
  "enabledPlugins": {
    "github-workflows@jasonkuhrt": true
  }
}
```

Team members automatically get the marketplace when they trust the project folder.

### Manual Install

```bash
/plugin marketplace add jasonkuhrt/claude-marketplace
/plugin install github-workflows@jasonkuhrt
```

## Development

For local development with immediate changes (no push required):

1. Clone the repo locally
2. Update `~/.claude/plugins/known_marketplaces.json`:

```json
{
  "jasonkuhrt": {
    "source": {
      "source": "directory",
      "path": "/path/to/claude-marketplace"
    },
    "installLocation": "/path/to/claude-marketplace",
    "autoUpdate": true
  }
}
```

3. Restart Claude Code

Changes to plugins are picked up immediately. Push to GitHub to share with others.

## Versioning

- Marketplace tracks main branch HEAD (no version pinning)
- Plugins are versioned via `version` field in `plugin.json`
- Bump version to trigger cache refresh for consumers
