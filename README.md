# Repolex Knowledge Graph of scrapy/pypydispatcher

RDF knowledge graph data for [scrapy/pypydispatcher](https://github.com/scrapy/pypydispatcher), parsed by [repolex](https://repolex.ai).

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
rlex download scrapy/pypydispatcher
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3bee78abf29e04ffd4ee73e7b2419f9c58a3c71c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3bee78abf29e04ffd4ee73e7b2419f9c58a3c71c
│           └── chunk-001.nq.gz
├── blob
│   ├── 004118d8653dbb069daf9ca4b465845326c2fdf8.nq.gz
│   ├── 006a3a3d671ca66e75f97b6c07740648a5c19e78.nq.gz
│   ├── 02576fcfe5316f8c03ca607cbd3684260d5fe0a9.nq.gz
│   ├── 0519da6df982a7d27c92e8e8e8b2d019c1f90571.nq.gz
│   ├── 051defdb509720d5a35aa807f8d8bed2313f1398.nq.gz
│   ├── 06f32b94e76daef6913fa4f568774bc459db00b5.nq.gz
│   ├── 0960a6073c6887d6894969609b46a5b31702a768.nq.gz
│   ├── 13928118c889d11fb7cd5220680f040c1f3cf507.nq.gz
│   ├── 191e76a58c51f1ca6909eacae5140b2c6e5886e1.nq.gz
│   ├── 29c64d23b48a72419d6b49fa153f1955d5421bf6.nq.gz
│   ├── 2c2b97d0da1d0bca89822f7588d53cf00012c8bb.nq.gz
│   ├── 3a44ea5161afb7d36415977c94d8a1e87eb35ad5.nq.gz
│   ├── 48552388911d26bd3403cdc0f886afd542ca9a58.nq.gz
│   ├── 558c5d2aedc66b144ffa397221666d35c35b8e72.nq.gz
│   ├── 61427e829c33185cc01d50ced41583e2f257a0ff.nq.gz
│   ├── 676ff8767d7b3a68efdb4ad7e54a10ed54aeb9a0.nq.gz
│   ├── 679895bb5c285f02ffd102c9d237f7ce5d164dbf.nq.gz
│   ├── 7b28baca4fc5e6f0d168c491119a0ffe5b4dfb41.nq.gz
│   ├── 8546b45d2bb8ed6051a575a2597de316e7a33a9d.nq.gz
│   ├── 889640e579d9819f7035e9593c6e2b906053fc3a.nq.gz
│   ├── 8e7427fe9be6b1105757977a9ced4482fa9321fb.nq.gz
│   ├── 923cbb48d35ad174dcc4cf3554ebac4654a003b4.nq.gz
│   ├── 925a9b93ea657cc7124c570dae9452e130411a67.nq.gz
│   ├── a68d418d5580d4c00b3419e18e55bd4654238722.nq.gz
│   ├── be266372ac3e48081a3e60ff093f8a1660eca44a.nq.gz
│   ├── c795d04be43a92fc9a8916143f10b2e2264b27e2.nq.gz
│   ├── cde9a34d592202dd3794e37ec1180d1613a4be33.nq.gz
│   ├── e8e047826c815fc54c678172b74425fe3f867136.nq.gz
│   ├── f506fab66a000e6fc1789b147031f5ee037e719d.nq.gz
│   └── f89f3e854a3cb8dd4d862e19a8158ae136e21587.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3bee78abf29e04ffd4ee73e7b2419f9c58a3c71c.nq.gz
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

[scrapy/pypydispatcher](https://github.com/scrapy/pypydispatcher)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
