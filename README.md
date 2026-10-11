# Repolex Knowledge Graph of tiangolo/label-approved

RDF knowledge graph data for [tiangolo/label-approved](https://github.com/tiangolo/label-approved), parsed by [repolex](https://repolex.ai).

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
rlex download tiangolo/label-approved
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 189338a34da6449ea0db0f4bea846cf2ca754f30
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 189338a34da6449ea0db0f4bea846cf2ca754f30
│           └── chunk-001.nq.gz
├── blob
│   ├── 0045fb8182cf94a55db192aa3bc8c4c7e033da47.nq.gz
│   ├── 0295827b7da1a7fd3e84bbd24ca2548871b51fb7.nq.gz
│   ├── 0ffc101a3f23548392499fe5104f3f8cf4d4e91b.nq.gz
│   ├── 1323c838f18bdab77014ca29910e337a79d1b714.nq.gz
│   ├── 4f7c3d01ef90180eac6b7aea49c70fa6b031e962.nq.gz
│   ├── 59ff54044c3c2fa9df771e5c2bc5359495c2cf7a.nq.gz
│   ├── 65e67cfb063afee5e324e7f9d4fba08d088883c1.nq.gz
│   ├── 6d0ca61c391c0d54fa97e1e8244139dea29c09cf.nq.gz
│   ├── ade122f400db4ef27bfe9748a3a2d32b80b3141b.nq.gz
│   ├── cc72dcd93da80544d3724bb329633f61c38bbf5e.nq.gz
│   ├── cd972a0ba47221bf96acedfaed8f3b5cba819849.nq.gz
│   ├── d025b2c67caa73aa9f0646fe879dfe32c4e9b781.nq.gz
│   ├── d535dc8c53b768076670f0c4408673cbeaeef7b1.nq.gz
│   ├── dde1c7a9dc8e0c551e57682c28ce2e9f1ac11bc3.nq.gz
│   ├── e3e989a4b4a03a9123d90ae02cadef5c4d7c8d7b.nq.gz
│   ├── e53209ee9e88aa0b213a0d68242ad46dc3c0c8c1.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fe887128231a6530ea79e916e1430772488d81b6.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 189338a34da6449ea0db0f4bea846cf2ca754f30.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 25 files
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

[tiangolo/label-approved](https://github.com/tiangolo/label-approved)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
