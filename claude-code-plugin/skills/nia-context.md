# Nia Context

Cross-agent context sharing.

## `context(action, ...)`

### Save
```
context(
  action="save",
  title="Auth Implementation",
  summary="Implemented JWT with refresh tokens",
  content="<full conversation>",
  agent_source="claude-code",
  tags=["auth", "backend"]
)
```

With references:
```
context(
  action="save",
  title="...",
  summary="...",
  content="...",
  agent_source="claude-code",
  nia_references={
    "indexed_resources": [{"identifier": "owner/repo", "resource_type": "repository"}],
    "search_queries": [{"query": "...", "key_findings": "..."}]
  },
  edited_files=[
    {"file_path": "src/auth.ts", "operation": "modified", "changes_description": "Added JWT"}
  ]
)
```

### List & Search
```
context(action="list")
context(action="list", query="auth")
context(action="search", query="authentication patterns")
```

### Retrieve
```
context(action="retrieve", context_id="uuid")
```

### Update & Delete
```
context(action="update", context_id="uuid", title="New Title")
context(action="delete", context_id="uuid")
```

## Handoff Flow
1. End of session: `context(action="save", ...)`
2. New session: `context(action="retrieve", context_id="...")`
