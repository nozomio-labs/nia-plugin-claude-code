# Nia Indexing

Index and manage external sources.

## Tools

### `index(url)`
Auto-detects type from URL.
```
index("https://github.com/owner/repo")           # Repository
index("https://docs.example.com")                 # Documentation  
index("2312.00752")                               # arXiv paper
```

Options: `branch`, `resource_type`, `url_patterns`, `exclude_patterns`

### `manage_resource(action, ...)`

| Action | Required Params | Example |
|--------|-----------------|---------|
| `list` | - | `manage_resource(action="list")` |
| `list` | `query` | `manage_resource(action="list", query="react")` |
| `status` | `resource_type`, `identifier` | `manage_resource(action="status", resource_type="repository", identifier="owner/repo")` |
| `rename` | `resource_type`, `identifier`, `new_name` | `manage_resource(action="rename", ...)` |
| `delete` | `resource_type`, `identifier` | `manage_resource(action="delete", ...)` |

`resource_type`: `"repository"` | `"documentation"` | `"research_paper"`

## Workflow
```
manage_resource(action="list")                    # See what's indexed
index("https://github.com/vercel/next.js")        # Index new
manage_resource(action="status", resource_type="repository", identifier="vercel/next.js")
```
