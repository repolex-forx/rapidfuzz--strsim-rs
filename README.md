# Repolex Knowledge Graph of rapidfuzz/strsim-rs

RDF knowledge graph data for [rapidfuzz/strsim-rs](https://github.com/rapidfuzz/strsim-rs), parsed by [repolex](https://repolex.ai).

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
rlex download rapidfuzz/strsim-rs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f72cd1cbbfc0b43db217a9c57c543b025bdba863
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── f72cd1cbbfc0b43db217a9c57c543b025bdba863.nq.gz
│   └── repolex
│       └── f72cd1cbbfc0b43db217a9c57c543b025bdba863
│           └── chunk-001.nq.gz
├── blob
│   ├── 0fbd4dc63032764b41f08d1c7b62d5de637b1a95.nq.gz
│   ├── 15c7041b6442a7d87af2ffd2294c611acdc67501.nq.gz
│   ├── 41ddad1a6b403a430df7ba03a89eb76e3ddd2a53.nq.gz
│   ├── 45d085112479a324def6360cc94439137de1d7e1.nq.gz
│   ├── 5ad4a63b0a0f37d201d15b610818a4c843765eab.nq.gz
│   ├── 62c879b5a544dc404b35dfcb3b9c4a13f8111b34.nq.gz
│   ├── 6a3b098ab35dbf34ccfd6a054100080441db241e.nq.gz
│   ├── 80cd9fefa098a056f5673ff985680aa1a134fbe2.nq.gz
│   ├── 8d1fbe1dce99c844df6c2c7c37c39616e22ed800.nq.gz
│   ├── 991fc6f5b5d65c3ab65324c5bd90a4c8b849ebce.nq.gz
│   ├── a81103dff234e572e32f9f987b80a8a1e0643475.nq.gz
│   ├── ba1f2ce891614d4053f750bd5a701a4d75216cac.nq.gz
│   ├── ee635471570ff03278f0eb2f1915d87be21488fd.nq.gz
│   └── ff6eca9e9bb2e4f4d04670c81616bdd439c59de7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f72cd1cbbfc0b43db217a9c57c543b025bdba863.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 23 files
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

[rapidfuzz/strsim-rs](https://github.com/rapidfuzz/strsim-rs)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
