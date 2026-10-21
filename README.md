# Repolex Knowledge Graph of astropy/astropy-integration-testing

RDF knowledge graph data for [astropy/astropy-integration-testing](https://github.com/astropy/astropy-integration-testing), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download astropy/astropy-integration-testing
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 53cc0065ff4dc8900a3db4446d5249d8ad818452
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 53cc0065ff4dc8900a3db4446d5249d8ad818452
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c55230d310a413817b32cedc9a11accd282c374.nq.gz
│   ├── 42d44ed051874a6db560c3394279cfe9b73ec82c.nq.gz
│   ├── 4e840617024ca81d8748e2c4bbf56d216c2bfff6.nq.gz
│   ├── 7417a4fa28bb804c04c7e0f7d250c29b281372f3.nq.gz
│   ├── 89326bb372d177bf996623f50beb2f8f6fa46fdd.nq.gz
│   ├── 9f7e2252ea73e44d8395f59d5bc05362358a4607.nq.gz
│   ├── c765c24e524a5ef9a4caaf41d20ff5698d2bc835.nq.gz
│   ├── d581eb97ca5cbcf12d651eb7b4e1e0af237fd45f.nq.gz
│   └── e79ca220f391f077e7300306c1a702e6b860092b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 53cc0065ff4dc8900a3db4446d5249d8ad818452.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 17 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[astropy/astropy-integration-testing](https://github.com/astropy/astropy-integration-testing)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
