# Repolex Knowledge Graph of aio-libs/aioga

RDF knowledge graph data for [aio-libs/aioga](https://github.com/aio-libs/aioga), parsed by [repolex](https://repolex.ai).

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
rlex download aio-libs/aioga
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── dbc0cbdae353826c532b3f7fc1a3ab4c063f08fa
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── dbc0cbdae353826c532b3f7fc1a3ab4c063f08fa
│           └── chunk-001.nq.gz
├── blob
│   ├── 0437599c8a6afd0994ecca6b1675f3eb88866160.nq.gz
│   ├── 0513c2b7e891b9f60b1f80c823aac6c5e3bc1db1.nq.gz
│   ├── 1bf3072dabbb2ef277a0732d317e657661775713.nq.gz
│   ├── 24744c3127520e018c23de0625e894c836fb5210.nq.gz
│   ├── 2613cde9ad315cb0ff374bb08ce5552a6fb3be74.nq.gz
│   ├── 4f277145b26be42a9797674c85efa3a462a56e75.nq.gz
│   ├── 84818b49b371f24b42256ba0c4d3fc53a9add1ea.nq.gz
│   ├── a49a0265f9fcb3e73282868d21521a23b8c1cd44.nq.gz
│   ├── a846ecd3c826383bcd148c0e70ab6cfe546ac87e.nq.gz
│   └── e24206f7951ce600070c653a55f024bdf4d78a08.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── dbc0cbdae353826c532b3f7fc1a3ab4c063f08fa.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 18 files
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

[aio-libs/aioga](https://github.com/aio-libs/aioga)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
