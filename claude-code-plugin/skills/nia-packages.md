# Nia Package Search

Search npm, PyPI, Crates.io package source code.

## `nia_package_search_hybrid(registry, package_name, semantic_queries, ...)`

Semantic search in package internals.

```
nia_package_search_hybrid(
  registry="npm",
  package_name="react",
  semantic_queries=["How does useState work?", "State update batching"]
)
```

```
nia_package_search_hybrid(
  registry="py_pi",
  package_name="fastapi",
  semantic_queries=["dependency injection"],
  pattern="Depends"  # Optional regex filter
)
```

Registries: `npm`, `py_pi`, `crates_io`, `golang_proxy`, `ruby_gems`

Options: `version`, `pattern` (regex), `language`

## Read Package Files

After finding relevant code, read full file:
```
nia_read(
  source_type="package",
  registry="npm",
  package_name="react",
  filename_sha256="<from search result>",
  start_line=1,
  end_line=100
)
```
