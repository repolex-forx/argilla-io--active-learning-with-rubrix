# Repolex Knowledge Graph of argilla-io/active-learning-with-rubrix

RDF knowledge graph data for [argilla-io/active-learning-with-rubrix](https://github.com/argilla-io/active-learning-with-rubrix), parsed by [repolex](https://repolex.ai).

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
rlex download argilla-io/active-learning-with-rubrix
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ef7f7ac2c80f6acc393a26edc7117fc78ce683e1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ef7f7ac2c80f6acc393a26edc7117fc78ce683e1
│           └── chunk-001.nq.gz
├── blob
│   ├── 165ebac9fc00e0c8e245e9868a5a909a82062500.nq.gz
│   ├── 2883c5772901f2a58b3a64b76b82b18b8f443529.nq.gz
│   ├── 4af4ba288a32ff906e63c8d20b5f9e79fae9d27e.nq.gz
│   ├── 80d38e4fe7b7657c6556283465173dbe8861261c.nq.gz
│   ├── ac797141c3f1aa8d2317122569d6b68739ca3430.nq.gz
│   ├── b6e47617de110dea7ca47e087ff1347cc2646eda.nq.gz
│   ├── e0effec05b602b63a6a6338afdff839737ccdcae.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ef7f7ac2c80f6acc393a26edc7117fc78ce683e1.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 15 files
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

[argilla-io/active-learning-with-rubrix](https://github.com/argilla-io/active-learning-with-rubrix)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
