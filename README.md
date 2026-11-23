# Repolex Knowledge Graph of huggingface/hf_transfer

RDF knowledge graph data for [huggingface/hf_transfer](https://github.com/huggingface/hf_transfer), parsed by [repolex](https://repolex.ai).

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
rlex download huggingface/hf_transfer
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 16bbc5045ff4036be9d8bcd0050108d82229a216
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 16bbc5045ff4036be9d8bcd0050108d82229a216.nq.gz
│   └── repolex
│       └── 16bbc5045ff4036be9d8bcd0050108d82229a216
│           └── chunk-001.nq.gz
├── blob
│   ├── 03c2ca7370340daee4296f3e2aaca80a46f2c725.nq.gz
│   ├── 078d9a901e5d410cfcf9d2f80e908bca02b42c65.nq.gz
│   ├── 23cdb316a96a2eddafc0021abb62f2a80bf8a3f6.nq.gz
│   ├── 3a93cdb7551917436862e96c8495380a57f2d5fd.nq.gz
│   ├── 7ebcf4c2d88eb947dd83944a04dfd0bd90407069.nq.gz
│   ├── 839e20090361518da064eedf575775f50fdb2660.nq.gz
│   ├── 83a22cd922a34d020d6dcfac3eace16e2c82c182.nq.gz
│   ├── 98f5731a66fcac01ff798880d5c396621400b3f7.nq.gz
│   ├── a6e6b9a66e5a0dee570596a510fcb459cd2811f2.nq.gz
│   ├── af3ca5ef1ca8475c73d9646a74967bf63f2fec96.nq.gz
│   ├── c19b9ff0ca4793a7871056fcf8b7acc23af6e0ea.nq.gz
│   ├── e6477729355d180783930e33641017b53194949c.nq.gz
│   └── f0e1b529eba52fd2f6db75e2fc61b674c2be4e54.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 16bbc5045ff4036be9d8bcd0050108d82229a216.nq.gz
├── filetree
│   └── 16bbc5045ff4036be9d8bcd0050108d82229a216.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 23 files
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

[huggingface/hf_transfer](https://github.com/huggingface/hf_transfer)

---
*Parsed on 2026-11-23 by [repolex](https://repolex.ai)*
