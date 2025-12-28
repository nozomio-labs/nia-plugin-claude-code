# Nia Explore & Read

Navigate and read indexed sources.

## Tools

### `nia_explore(source_type, action, ...)`

**Repository tree:**
```
nia_explore(source_type="repository", repository="owner/repo", action="tree")
nia_explore(source_type="repository", repository="owner/repo", action="tree", include_paths=["src/"])
```

**Documentation tree/ls:**
```
nia_explore(source_type="documentation", doc_source_id="uuid", action="tree")
nia_explore(source_type="documentation", doc_source_id="uuid", action="ls", path="/api")
```

Options: `branch`, `include_paths`, `exclude_paths`, `file_extensions`

### `nia_read(source_type, ...)`

**Repository file:**
```
nia_read(source_type="repository", source_identifier="owner/repo:src/auth.ts")
```

**Documentation page:**
```
nia_read(source_type="documentation", doc_source_id="uuid", path="/api/auth.md")
```

**Package file:**
```
nia_read(source_type="package", registry="npm", package_name="react", filename_sha256="abc123", start_line=1, end_line=100)
```

## Workflow
```
nia_explore(source_type="repository", repository="vercel/next.js", action="tree")
nia_read(source_type="repository", source_identifier="vercel/next.js:packages/next/src/server/router.ts")
```
