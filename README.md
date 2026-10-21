# Repolex Knowledge Graph of pydata/compilers-webpage

RDF knowledge graph data for [pydata/compilers-webpage](https://github.com/pydata/compilers-webpage), parsed by [repolex](https://repolex.ai).

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
rlex download pydata/compilers-webpage
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 146432378f69e7cecbef24f8eeb508bff0f10237
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 146432378f69e7cecbef24f8eeb508bff0f10237
│           └── chunk-001.nq.gz
├── blob
│   ├── 219b76fec32df28d99ddc339cf3413ded801f3c1.nq.gz
│   ├── 3bf6484a29d8da269f9bc874b25493a45fae3bae.nq.gz
│   ├── 3e52b089a222cdfd620809f560a08a3c153c2a92.nq.gz
│   ├── 478f8b95566b7b444c0440d325274b28c9a113c0.nq.gz
│   ├── 4a701e3c6d22d362081efae8ae365c4531d0dca7.nq.gz
│   ├── 4f52742b7b333c5f3a33366259f866062e6c983d.nq.gz
│   ├── 4f61b7f1bb99b6727cf57a38286292f95d2cb44e.nq.gz
│   ├── 6d1f112c5a6c31f02234ae523910176f0fd32ad2.nq.gz
│   ├── 747eb2095ea5e36f82a8fda5b964eb6a1eba6388.nq.gz
│   ├── 8349aee86de27b035590c9fd80d4583a7c0a7f5a.nq.gz
│   ├── a4c7f06637fb296866337925bb993f3ad1da7adf.nq.gz
│   ├── a9969993201f9cee63cf9f49217646347297b643.nq.gz
│   ├── b3ce5c0d611b4804d31b4c30eedfa9ab9a39a461.nq.gz
│   ├── ca217d87767bed99503fa34b0b4a740f30606af3.nq.gz
│   ├── da09685eb8b3d5fbceff79147cb7f42e8f7640fa.nq.gz
│   ├── daa9ab8543dee583e86a6b9d365e17c269592810.nq.gz
│   ├── daafa9180839e91a5f5a5e96cd560d45c4ac50b4.nq.gz
│   ├── e254f8f6d4a0f882dacce463c671e524bbd5187b.nq.gz
│   ├── eb2050fa12e9d7f56e8a3038c2bfe6bc603c8271.nq.gz
│   ├── ef6f576b4409d39a9f46fc9c29bc841b9b0d8d3c.nq.gz
│   └── f97292bc9df81402876bdca2d633e11d53280f77.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 146432378f69e7cecbef24f8eeb508bff0f10237.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[pydata/compilers-webpage](https://github.com/pydata/compilers-webpage)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
