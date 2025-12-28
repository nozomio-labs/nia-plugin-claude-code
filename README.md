# Nia - Claude Code Plugin

Connect Claude Code to [Nia](https://trynia.ai) - the up-to-date knowledge API for AI agents. Index repositories, search codebases, and share context across agents.


## Installation

### Step 1: Get Your API Key

1. Sign up at [app.trynia.ai](https://app.trynia.ai)
2. Go to [API Keys](https://app.trynia.ai/api-keys)
3. Create a new key (starts with `nk_`)

### Step 2: Set Your API Key

**Option A: `.env` File (Recommended)**

Create a `.env` file in your home directory or project:
```bash
# ~/.env or ~/project/.env
NIA_API_KEY=nk_xxxxxxxxxxxxxxxx
```

**Option B: Shell Profile**

Add to your `~/.zshrc` or `~/.bashrc`:
```bash
export NIA_API_KEY=nk_xxxxxxxxxxxxxxxx
```

Then reload: `source ~/.zshrc`

**Option C: Per-Session**
```bash
NIA_API_KEY=nk_xxxxxxxxxxxxxxxx claude
```

### Step 3: Install Plugin

**Option 1: Install from Git (Recommended)**

```bash
claude plugin install https://github.com/nozomio-labs/nia-plugin-claude-code
```

**Option 2: Install from Marketplace**

```bash
claude plugin marketplace add https://raw.githubusercontent.com/nozomio-labs/nia-plugin-claude-code/main/marketplace.json
claude plugin install nia
```

**Option 3: Local Development**

```bash
git clone https://github.com/nozomio-labs/nia-plugin-claude-code
claude --plugin-dir ./nia-plugin-claude-code
```

### Verify Installation

```bash
# Check MCP server is connected
claude mcp list
# Should show: nia

# In Claude Code, try:
# "List my indexed Nia resources"
```

## Quick Start

### Index a Repository
```
index("https://github.com/vercel/next.js")
```

### Search Codebases
```
search("How does the App Router handle routing?", repositories=["vercel/next.js"])
```

### Universal Search (All Public Sources)
```
search("React Server Components implementation")
```

### Save Context for Handoff
```
context(action="save", title="...", summary="...", content="...", agent_source="claude-code")
```

## Available Tools

| Tool | Description |
|------|-------------|
| `index` | Index repos, docs, or research papers |
| `search` | Semantic search across indexed sources |
| `manage_resource` | List, status, rename, delete resources |
| `nia_read` | Read file content from indexed sources |
| `nia_grep` | Regex search in indexed sources |
| `nia_explore` | Tree view and directory listing |
| `nia_research` | Web search, deep research, oracle mode |
| `nia_package_search_hybrid` | Semantic search in packages |
| `context` | Save/retrieve cross-agent context |

## Skills Included

- **nia-index** - Index repositories, docs, and papers
- **nia-search** - Semantic and regex search
- **nia-explore** - Tree views and file reading
- **nia-research** - Web search and deep research
- **nia-packages** - Package source code search
- **nia-context** - Cross-agent context handoff

## Documentation

- [Nia Docs](https://docs.trynia.ai)
- [Claude Code MCP Guide](https://code.claude.com/docs/en/mcp)
- [Plugin Reference](https://code.claude.com/docs/en/plugins-reference)

## Support

- [GitHub Issues](https://github.com/nozomio-labs/nia-plugin-claude-code/issues)
- [Documentation](https://docs.trynia.ai)

## License

AGPL-3.0 - See [LICENSE](LICENSE)
