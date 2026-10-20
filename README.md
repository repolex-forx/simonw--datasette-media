# Repolex Knowledge Graph of simonw/datasette-media

RDF knowledge graph data for [simonw/datasette-media](https://github.com/simonw/datasette-media), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/datasette-media
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 99714794a0ef58e9808f68bf752a8b934591d832
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 99714794a0ef58e9808f68bf752a8b934591d832
│           └── chunk-001.nq.gz
├── blob
│   ├── 0655464557e475570059e126c5d01ad5cfe6897e.nq.gz
│   ├── 170da122d3d1a2d30462b6e39adfed750c463540.nq.gz
│   ├── 2495cbc3b5f21bcb2752eb5b3a6e786f26be2965.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 4e6e59618eb2303bf19c86122908f2529f4448cf.nq.gz
│   ├── 5f2be2129da671fe1bf2e629bc8cff97225aba18.nq.gz
│   ├── 7f7e6888359dfbeb1d39c5196ab99496f95a58c8.nq.gz
│   ├── a44e99771bd675e888566265c681fc149bf9a202.nq.gz
│   ├── b87fae6693af94b526b3c6f45af49e5bcb5fdf74.nq.gz
│   ├── e683f42f43bb8a637d160105dede9eb232ba1417.nq.gz
│   └── ed21a58584e2766b41d5c9e60465aaa1404939ed.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 99714794a0ef58e9808f68bf752a8b934591d832.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
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

[simonw/datasette-media](https://github.com/simonw/datasette-media)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
