# Repolex Knowledge Graph of NousResearch/hermes-plugin-openviking

RDF knowledge graph data for [NousResearch/hermes-plugin-openviking](https://github.com/NousResearch/hermes-plugin-openviking), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/hermes-plugin-openviking
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5dca75f4d3dcef9467ce2ff32e170d84c679de5f
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 5dca75f4d3dcef9467ce2ff32e170d84c679de5f.nq.gz
│   └── repolex
│       └── 5dca75f4d3dcef9467ce2ff32e170d84c679de5f
│           └── chunk-001.nq.gz
├── blob
│   ├── 00f2d38d8063d0c6b219c0081e51888063b0c55e.nq.gz
│   ├── 130220f5162c198bbe7317044184bf4c4edba82c.nq.gz
│   ├── 18b8ea78741548dac1d4e52df7ad130ef84bc848.nq.gz
│   ├── 2b41a9f12ff428b71160237523fd71fa2e6f9c0c.nq.gz
│   ├── 3578e9be8f3f4c3a218b100cc4095850bdd29de5.nq.gz
│   ├── 75410e73319c72cd3e991a501c5455eb78f38375.nq.gz
│   ├── 8e8b0d3d969a9367d002c6a0dc00b37631da712b.nq.gz
│   └── ad8a96256100c13f49122b0e118ceb2b2c12fed5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 5dca75f4d3dcef9467ce2ff32e170d84c679de5f.nq.gz
├── filetree
│   └── 5dca75f4d3dcef9467ce2ff32e170d84c679de5f.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 16 files
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

[NousResearch/hermes-plugin-openviking](https://github.com/NousResearch/hermes-plugin-openviking)

---
*Parsed on 2026-09-29 by [repolex](https://repolex.ai)*
