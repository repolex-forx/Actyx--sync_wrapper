# Repolex Knowledge Graph of Actyx/sync_wrapper

RDF knowledge graph data for [Actyx/sync_wrapper](https://github.com/Actyx/sync_wrapper), parsed by [repolex](https://repolex.ai).

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
rlex download Actyx/sync_wrapper
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ec3abb02497d85698d805ea8bcb5d2ef97b81303
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── ec3abb02497d85698d805ea8bcb5d2ef97b81303.nq.gz
│   └── repolex
│       └── ec3abb02497d85698d805ea8bcb5d2ef97b81303
│           └── chunk-001.nq.gz
├── blob
│   ├── 20261c93727c58b369ba41cb2ca047c4a9b8eaed.nq.gz
│   ├── 2800d9a7328909c83b92fc099906778a19f01de1.nq.gz
│   ├── 96ef6c0b944e24fc22f51f18136cd62ffd5b0b8f.nq.gz
│   ├── c0209a15de8d8d99c949e105b8c5390793890655.nq.gz
│   └── f433b1a53f5b830a205fd2df78e2b34974656c7b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── ec3abb02497d85698d805ea8bcb5d2ef97b81303.nq.gz
├── filetree
│   └── ec3abb02497d85698d805ea8bcb5d2ef97b81303.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 15 files
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

[Actyx/sync_wrapper](https://github.com/Actyx/sync_wrapper)

---
*Parsed on 2026-11-21 by [repolex](https://repolex.ai)*
