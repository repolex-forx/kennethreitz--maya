# Repolex Knowledge Graph of kennethreitz/maya

RDF knowledge graph data for [kennethreitz/maya](https://github.com/kennethreitz/maya), parsed by [repolex](https://repolex.ai).

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
rlex download kennethreitz/maya
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9766619d007caf553357db6dba5485fb36ed4edd
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9766619d007caf553357db6dba5485fb36ed4edd
│           └── chunk-001.nq.gz
├── blob
│   ├── 0ed1267c8e278cd304d0c63a59fc361ae6263e07.nq.gz
│   ├── 0f79d00df7cee50c7657a46ba37a6f847d4674b7.nq.gz
│   ├── 1ead83807972451c7b74d15655334aa1d470423c.nq.gz
│   ├── 1f8730e07a872ed447f4f88b4ca682d4d14a6800.nq.gz
│   ├── 2de3df642dc739fb279fa5999673fbdfa454a75b.nq.gz
│   ├── 2f05245671509288bf29e4095897ff9c0707c78f.nq.gz
│   ├── 35689f67d2caf6f04b6d736a80d312ee4428fd7c.nq.gz
│   ├── 39c105a2f687b2536cebfd14d7e1e012c9aa4c16.nq.gz
│   ├── 4e9537eac1c3f42a4ed2c3067b1345d9fe828aba.nq.gz
│   ├── 4fbc845e0b0b0fe66eb372b4c96a0295d8c73986.nq.gz
│   ├── 6ac4ada4810edd5f2a5952148b773e3f9144b4ce.nq.gz
│   ├── 777cd88e1d0bc5160faccaf0f0563ae039355c57.nq.gz
│   ├── 797cce048f63aa2165c564251330f6895a6dc4a2.nq.gz
│   ├── 7d948e338da827386c063b071d8657d03911e269.nq.gz
│   ├── 98e081917bc04dfb9b7f5e9a72ac8cc09065b531.nq.gz
│   ├── 9f3695ae481f9a5e4c2fef4f34433eacb76a73f3.nq.gz
│   ├── a3da4014d4bf14411c4e147854548dcdd8325a6c.nq.gz
│   ├── a77e430fb678a14803ff68831e56417ec26d42f8.nq.gz
│   ├── aa73f3389369664fd072457f7aff3013cfc0692e.nq.gz
│   ├── acc02a17160a8fa61a467b30885f636975f98c95.nq.gz
│   ├── b445631d584dacf88568494cca012fe6db6e78a3.nq.gz
│   ├── bd74f8066ac01e4d70354161eaaccb0a3a3e37e9.nq.gz
│   ├── c5c33c99f8ddead17238cd017ea0e48641d2bf5c.nq.gz
│   ├── dec8afd34883665b8bc85f277b7476e083810c38.nq.gz
│   ├── e10ff5145a8643ff081939a5a6b72aa642673295.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f15978b0fc6cf0f01d282715a49e47b2cc5bec8b.nq.gz
│   ├── f1f82e6effeb41ed212a3713cc74868bd400c73b.nq.gz
│   ├── f747af2536ddffe721a8d83084feac9d93eeadfa.nq.gz
│   └── fba7788141ce7070a04c02cd3341b4da227b5a93.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9766619d007caf553357db6dba5485fb36ed4edd.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 38 files
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

[kennethreitz/maya](https://github.com/kennethreitz/maya)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
