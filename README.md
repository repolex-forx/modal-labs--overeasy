# Repolex Knowledge Graph of modal-labs/overeasy

RDF knowledge graph data for [modal-labs/overeasy](https://github.com/modal-labs/overeasy), parsed by [repolex](https://repolex.ai).

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
rlex download modal-labs/overeasy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 85885c6c61128d897124f795a833726115db7d3f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 85885c6c61128d897124f795a833726115db7d3f
│           └── chunk-001.nq.gz
├── blob
│   ├── 02641d9e5c3b26dbeea16c5d683c5fdaa9e667e7.nq.gz
│   ├── 18c88e186946ca848456dd2f1023fa1f05d9f886.nq.gz
│   ├── 1dd41b6b1826b235a7700b26e4458a2cee99f7db.nq.gz
│   ├── 3a5d1cbd97a71d2e38c59eeac634cbd5ec3bdf24.nq.gz
│   ├── 5d24ff14b48ce89c8b9e3865f120c8ea685630ea.nq.gz
│   ├── 6324d401a069f4020efcf0ff07442724b52f47c2.nq.gz
│   ├── ab03921b35ba5618ab6cf6800d863337984d9ad5.nq.gz
│   ├── ec12692c6c98fd363a86799323f8e2b16988f72b.nq.gz
│   └── f8e3b0c5f3e99b0b1e403693db9cb6d05867055c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 85885c6c61128d897124f795a833726115db7d3f.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 16 files
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

[modal-labs/overeasy](https://github.com/modal-labs/overeasy)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
