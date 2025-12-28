# Nia Search

Semantic and regex search across indexed sources.

## Tools

### `search(query, ...)`
Semantic search. Omit sources for universal search.
```
search("How does routing work?")                              # Universal (all public)
search("auth implementation", repositories=["owner/repo"])    # Specific repo
search("API usage", data_sources=["source-uuid"])             # Specific docs
```

Options: `search_mode` (`unified`|`repositories`|`sources`), `include_sources`

### `nia_grep(source_type, pattern, ...)`
Regex search. Faster for exact patterns.

**Repository:**
```
nia_grep(source_type="repository", repository="owner/repo", pattern="class.*Auth")
```

**Documentation:**
```
nia_grep(source_type="documentation", doc_source_id="uuid", pattern="webhook")
```

**Package:**
```
nia_grep(source_type="package", registry="npm", package_name="react", pattern="useState")
```

Options: `path`, `context_lines`, `case_sensitive`, `output_mode` (`content`|`files_with_matches`|`count`)

## When to Use
- **search** → concepts, questions, "how does X work?"
- **nia_grep** → exact patterns, function names, class definitions
