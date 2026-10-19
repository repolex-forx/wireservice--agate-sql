# Repolex Knowledge Graph of wireservice/agate-sql

RDF knowledge graph data for [wireservice/agate-sql](https://github.com/wireservice/agate-sql), parsed by [repolex](https://repolex.ai).

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
rlex download wireservice/agate-sql
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 20d796c8c112accfe7be8821e5acdb75fccd0f18
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 20d796c8c112accfe7be8821e5acdb75fccd0f18
│           └── chunk-001.nq.gz
├── blob
│   ├── 04a369c4279bb5f98ce45d4f8e8b81408f5844b7.nq.gz
│   ├── 0970f80c63234a4d2cd615b1ef1cd6de2c33f8b7.nq.gz
│   ├── 123014908bebbfb7ecfa1d15daaceb272fabe05b.nq.gz
│   ├── 12cf52cd714752c3698b0bdf1e807652631b549a.nq.gz
│   ├── 2d280ce9d6526789a1b31410f3b80cc949753e81.nq.gz
│   ├── 2d326df298bb4c35ee3ba51f687138a154769b41.nq.gz
│   ├── 404fa1e00835050bb7c933859eecf5826b208d63.nq.gz
│   ├── 43941de4376b013e022377a3160e0a494e9806e1.nq.gz
│   ├── 5ba382f07b8ac06f59d8bf2862a5520b1ccf07d1.nq.gz
│   ├── 5f596abc675d6f9552fbabcd11c5a6548b7615a8.nq.gz
│   ├── 65e9bc9f5a06fb2911b57dc540b6edc9a6301f5f.nq.gz
│   ├── 6d13fb5faaa10d3c6eaaa10e67a44be792fb2912.nq.gz
│   ├── 82ace4015c6b306af57f014824daf04f160d1fb0.nq.gz
│   ├── 838ede1ee35093fa7185df3f8680b08d5f93ba81.nq.gz
│   ├── 839f016fe83f4c17040d69fec5558569164204db.nq.gz
│   ├── 86daa6f58741be1eda3a04e738e3ef726abd24ab.nq.gz
│   ├── 8f557394919bbef5583a720b199d0fbd329a9efb.nq.gz
│   ├── 98c6c81f6d6ee770355d83e2197a671592ddc4e3.nq.gz
│   ├── a669e4fa308643e106c6b3df7d0387783eeaa4f2.nq.gz
│   ├── b6b0e03eaf739512f3075d18688b6e373f9fb528.nq.gz
│   ├── c375686c857b409c44990eaf3e288871143bdb46.nq.gz
│   ├── d28ed2483899b1b3d87f4d977d2b0267e8d8c2a7.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fe9fd3a18517bf1b6e26bff08ca4a593ba515a84.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 20d796c8c112accfe7be8821e5acdb75fccd0f18.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 32 files
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

[wireservice/agate-sql](https://github.com/wireservice/agate-sql)

---
*Parsed on 2026-10-19 by [repolex](https://repolex.ai)*
