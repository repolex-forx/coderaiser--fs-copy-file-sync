# Repolex Knowledge Graph of coderaiser/fs-copy-file-sync

RDF knowledge graph data for [coderaiser/fs-copy-file-sync](https://github.com/coderaiser/fs-copy-file-sync), parsed by [repolex](https://repolex.ai).

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
rlex download coderaiser/fs-copy-file-sync
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 99bc169db74ac2b165c4f19cb3a6013d33797451
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 99bc169db74ac2b165c4f19cb3a6013d33797451.nq.gz
│   └── repolex
│       └── 99bc169db74ac2b165c4f19cb3a6013d33797451
│           └── chunk-001.nq.gz
├── blob
│   ├── 020324da70252a0abe6347cacb2be75bd02caf1f.nq.gz
│   ├── 1ab82a482247e4510c12e2b90f4af041f7431b9e.nq.gz
│   ├── 44ec4e3d7eb3766ace3bf52e5ddd517f35e45fdc.nq.gz
│   ├── 6eb8370b0d8310b0e3a6b5069380d738e3218226.nq.gz
│   ├── 71ef0e9631fd27a63d24d6b32a76b6bbcfe4101c.nq.gz
│   ├── 7fdbf74529a5d3cf4f50653c267a62635dc8b9b9.nq.gz
│   ├── c2c2daf476506c3252b54edc7b316c0c074e168f.nq.gz
│   ├── ce013625030ba8dba906f756967f9e9ca394464a.nq.gz
│   ├── e5b60d3cbfcc812ce5135393d78a5a51a2a33129.nq.gz
│   ├── eaec9a10f8ba967fcd90b3bf0332a5b7d025ce1e.nq.gz
│   └── ff2aabb09a3a9f890549ef67d3efba609becfbd3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 99bc169db74ac2b165c4f19cb3a6013d33797451.nq.gz
├── filetree
│   └── 99bc169db74ac2b165c4f19cb3a6013d33797451.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 21 files
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

[coderaiser/fs-copy-file-sync](https://github.com/coderaiser/fs-copy-file-sync)

---
*Parsed on 2026-11-21 by [repolex](https://repolex.ai)*
