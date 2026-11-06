# Repolex Knowledge Graph of sphinx-contrib/redirects

RDF knowledge graph data for [sphinx-contrib/redirects](https://github.com/sphinx-contrib/redirects), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/redirects
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0706edbce3e9fb66ece8e66b912a15a5c53dae10
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0706edbce3e9fb66ece8e66b912a15a5c53dae10
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a25909c21b81e50aafbb46ef7f843fcb3dd6ddb.nq.gz
│   ├── 0f26f9ce980e62d71a2e255ed9e28f748238d2da.nq.gz
│   ├── 157d31cef509c985a2e144f8fa797647561ac6ea.nq.gz
│   ├── 1769f0d939b3176205e0b8bff67ea0bccf50d1b8.nq.gz
│   ├── 1fc785d4792e26578233e7e789e86aac21df29eb.nq.gz
│   ├── 2bb600dd040a556fa4141db6ffe03fe31eab383f.nq.gz
│   ├── 2cd1b029c48bd1139d7048ab4fcdd39eff878a31.nq.gz
│   ├── 4fc82028780f8bbb01563baa436b4b2ede636aba.nq.gz
│   ├── 6642c8b3fb41e1413f3547d95e2c2375219a3d7c.nq.gz
│   ├── 748ed1537a2f86aabe04c733873d03bdce1ce7dc.nq.gz
│   ├── 9b528dda2a99eb70414c263a726fef91dc3d37a3.nq.gz
│   ├── a5f6a809c1debde58ec12bf9c15b678f20c2c6c1.nq.gz
│   ├── ae0f862b865ef2f17cee6a962d8fb480d7229488.nq.gz
│   ├── b956c06fd54fe415d3d7c7532bf5bcd70358a010.nq.gz
│   ├── d50e18282d17cecc65f0fa707f36e150f34a504f.nq.gz
│   ├── e079f8a6038dd2dc8512967540f96ee0de172067.nq.gz
│   ├── e07c86783cefc86e86d723f307691fdfcdc51999.nq.gz
│   ├── eb634e5f9abd83a611aea8cd0a08b565a4a6702d.nq.gz
│   ├── f0e7087c00a9fc3469d7f56d9c3f1843a213df60.nq.gz
│   └── f81c30bc4bbe5600999cdb569048c59fe84d96e0.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0706edbce3e9fb66ece8e66b912a15a5c53dae10.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
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

[sphinx-contrib/redirects](https://github.com/sphinx-contrib/redirects)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
