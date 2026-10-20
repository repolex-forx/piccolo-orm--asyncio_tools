# Repolex Knowledge Graph of piccolo-orm/asyncio_tools

RDF knowledge graph data for [piccolo-orm/asyncio_tools](https://github.com/piccolo-orm/asyncio_tools), parsed by [repolex](https://repolex.ai).

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
rlex download piccolo-orm/asyncio_tools
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 08948b436c2e0bd93bfb6f68100f82ae07faad8e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 08948b436c2e0bd93bfb6f68100f82ae07faad8e
│           └── chunk-001.nq.gz
├── blob
│   ├── 2ca48513f80ffa0f806255fac9fbf8c2d109a035.nq.gz
│   ├── 2de1f24445b161821c3b6c9278088b82e273b77e.nq.gz
│   ├── 333d7850b9d8bcfa26bbcb58aa32fc0cd5696f06.nq.gz
│   ├── 3c0a461abe1d51891f6dac615139e065ac739bb5.nq.gz
│   ├── 3fcf8c2e727c29df76f0b54e8dfd4dde7965ab72.nq.gz
│   ├── 41e6263003062bd481320a5ff81596a971652e14.nq.gz
│   ├── 61dcbd41b3b9fe8233b28fffa4a65f9f3d7463ad.nq.gz
│   ├── 63ca51509be00ca893e4ab00de40caa028eca32e.nq.gz
│   ├── 72fd0658ad607c6f6423fc85e6fc8595d2b5b956.nq.gz
│   ├── 8e47adc1927567e9e6449c744b73f7f4613b7bcb.nq.gz
│   ├── 95c5735b3d62dda5c0898557045df36ede9a5901.nq.gz
│   ├── 97ec629cab760ceeb75da11d0934fb72f0586d14.nq.gz
│   ├── 9daa9e22a501e2c5e8dfe2a0b87bc673ab648f56.nq.gz
│   ├── c2756e072d7099d1a8175749e572c4a899a7a85e.nq.gz
│   ├── c43710dca67d3e99a409e5e4ea1949f8c9c0f0aa.nq.gz
│   ├── e079f8a6038dd2dc8512967540f96ee0de172067.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 08948b436c2e0bd93bfb6f68100f82ae07faad8e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[piccolo-orm/asyncio_tools](https://github.com/piccolo-orm/asyncio_tools)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
