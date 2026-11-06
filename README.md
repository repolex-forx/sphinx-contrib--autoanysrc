# Repolex Knowledge Graph of sphinx-contrib/autoanysrc

RDF knowledge graph data for [sphinx-contrib/autoanysrc](https://github.com/sphinx-contrib/autoanysrc), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/autoanysrc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 481f1285f0da6755a3253ef229f323ae272da1bb
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 481f1285f0da6755a3253ef229f323ae272da1bb
│           └── chunk-001.nq.gz
├── blob
│   ├── 05e5809710b789246d54ac703e2dd3a5a0886ac0.nq.gz
│   ├── 153aeaa26bc03532d5128110da5e7d020f6b0c56.nq.gz
│   ├── 3b6e9595a6ff00a934886fc220a3dccbeee5ea20.nq.gz
│   ├── 3df891dd56d28fac2fd0f2bef1c9f99c33344caa.nq.gz
│   ├── 70b19fa55154b7c4ecd55b64865d4bdb8e87d646.nq.gz
│   ├── 81d1564c9d42adf55018107db5d3d5646b3ed69e.nq.gz
│   ├── 9ac636ff4acb232a457f56e2fbb37c024969e974.nq.gz
│   ├── acc49147dec2f023de6722c190b25252b865b265.nq.gz
│   ├── b3788624762da0be102c188233ff686dfda891b9.nq.gz
│   ├── b988ff481f1bd63701c0bbf88f46c776f0e92f6a.nq.gz
│   ├── c365059d1bf34a2d33ebe18e89fb126d0da9e9f4.nq.gz
│   ├── c8bb531b3d141d75e518d1ebb48735f3138983f9.nq.gz
│   ├── e0dafce3f89e25966a83fe2822e9a8fad4b4f57b.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ed127a2453a54ba46dfc9ff098db10097a808ec1.nq.gz
│   └── f0717fe9b6d7b55feebf3ef1e66a15c387eaf6fc.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 481f1285f0da6755a3253ef229f323ae272da1bb.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 24 files
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

[sphinx-contrib/autoanysrc](https://github.com/sphinx-contrib/autoanysrc)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
