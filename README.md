# Repolex Knowledge Graph of bokeh/bokeh-fastapi

RDF knowledge graph data for [bokeh/bokeh-fastapi](https://github.com/bokeh/bokeh-fastapi), parsed by [repolex](https://repolex.ai).

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
rlex download bokeh/bokeh-fastapi
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 15c8ae0dda6d661c10f730ea7ffdfc99b1ff637d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 15c8ae0dda6d661c10f730ea7ffdfc99b1ff637d
│           └── chunk-001.nq.gz
├── blob
│   ├── 15a5512a066bb8164eb4f607c8d66d58568068c0.nq.gz
│   ├── 4a21d2d6a8e4ba0ce3fc8a66e179b0a06df0e097.nq.gz
│   ├── 50d64161f99f0c564a0d7266524d00f84708bb58.nq.gz
│   ├── 6bf9b98f89f5cd64cfa621b6bcc8eb88611e8f70.nq.gz
│   ├── 8c9a2aea472e02d9d21cd7cbe70b694dd8e7edf5.nq.gz
│   ├── cacf6338d1afc0af4424070efc51640f6f84faa1.nq.gz
│   └── fc44179b379540be02b27570d7678bf058283d3b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 15c8ae0dda6d661c10f730ea7ffdfc99b1ff637d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 15 files
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

[bokeh/bokeh-fastapi](https://github.com/bokeh/bokeh-fastapi)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
