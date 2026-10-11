# Repolex Knowledge Graph of samuelcolvin/call-alert

RDF knowledge graph data for [samuelcolvin/call-alert](https://github.com/samuelcolvin/call-alert), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/call-alert
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 388511b0a57ec1c82f5180a4b33a569f05f3c3aa
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 388511b0a57ec1c82f5180a4b33a569f05f3c3aa
│           └── chunk-001.nq.gz
├── blob
│   ├── 21cbc2cbfd0a2e479a01f3d49b8b4138d92b45cf.nq.gz
│   ├── 239354d60810976a72871361d63cb092eafac593.nq.gz
│   ├── 24ee5b1be9961e38a503c8e764b7385dbb6ba124.nq.gz
│   ├── 353fe668e7632ed977d582d8ae88803d4c27988d.nq.gz
│   ├── 38373578aeea4a62998eafc45900089cae0f5f38.nq.gz
│   ├── 69314ea26d9d06cc08d07da5378b092a726a6919.nq.gz
│   ├── 7cafda763f0325f647f30ea0d31bb503dc613d29.nq.gz
│   ├── e461edf465b086253c0a702a314dc12667aaf89e.nq.gz
│   ├── e4eb47a5c4cc028ea760659c5e6a826648cc8685.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 388511b0a57ec1c82f5180a4b33a569f05f3c3aa.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 16 files
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

[samuelcolvin/call-alert](https://github.com/samuelcolvin/call-alert)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
