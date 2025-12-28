# Nia Research

AI-powered research modes.

## `nia_research(query, mode, ...)`

### Quick (Web Search)
```
nia_research(query="React state management", mode="quick")
nia_research(query="FastAPI tutorials", mode="quick", category="github", num_results=10)
```
Categories: `github`, `company`, `research paper`, `news`, `tweet`, `pdf`

Options: `days_back`, `find_similar_to`

### Deep (AI Agent)
```
nia_research(query="Compare Zustand vs Jotai", mode="deep")
nia_research(query="Best practices for...", mode="deep", output_format="comparison table")
```

### Oracle (Autonomous)
Full research using your indexed sources.
```
nia_research(
  query="How to implement auth?",
  mode="oracle",
  repositories=["owner/repo"],
  data_sources=["uuid"]
)
```

## When to Use
- **quick** → find repos, docs, get links fast
- **deep** → analysis, comparisons, structured output
- **oracle** → deep dive using your specific indexed sources
