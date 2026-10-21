# Repolex Knowledge Graph of joblib/joblib-spark

RDF knowledge graph data for [joblib/joblib-spark](https://github.com/joblib/joblib-spark), parsed by [repolex](https://repolex.ai).

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
rlex download joblib/joblib-spark
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6e9931f7a1bb2387845f5d78d3ba312ae5585bfe
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6e9931f7a1bb2387845f5d78d3ba312ae5585bfe
│           └── chunk-001.nq.gz
├── blob
│   ├── 09fa80273f38d511bc6ebd330f18e75c8fe9ae13.nq.gz
│   ├── 140421409295baeb1e6ce8caab3907be861f342c.nq.gz
│   ├── 15c038d274fc39a7cd574e9eede35121ee23f404.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 337c42c185d43a2b42792f3081d1cd08cbfc5520.nq.gz
│   ├── 4751a114d20160249a37cb28ffcd1e0d33dadc32.nq.gz
│   ├── 5218130f851a6964baa1b383eb6a5bb5d3088717.nq.gz
│   ├── 56fe575efb83008f93918ceb164357761ad042c6.nq.gz
│   ├── 60c6ce52c7e1cc2f70f09b86a1b3387041a99cb9.nq.gz
│   ├── 61583f56e9375a77961452f446d424e56e734ca5.nq.gz
│   ├── 6491bacaecb1ed8ae429539d1f82eaf90ee2e540.nq.gz
│   ├── 67706f401bf649eee009a026ff581a47edde27e0.nq.gz
│   ├── 6897ea3008ec67ee741816123b1f0e6494e03ac5.nq.gz
│   ├── 6a776c9728654a7ca699630471263f94c1e73dc0.nq.gz
│   ├── 6aee43fb5cf60b07fceff69d659deac74e12047b.nq.gz
│   ├── 7d7565860c1f52be935bbe335874479a03f07745.nq.gz
│   ├── 8afc8b9a88b22b1eb997129d637d1baf9cf06607.nq.gz
│   ├── 8b391ad9fcc6a4edab0ec167bb11b516c80b00ab.nq.gz
│   ├── 93b430e3d70a10631e876dc0e7c0a4f064c1b5fc.nq.gz
│   ├── 960abf7d2d8e90eea1c2a668db79619bc1227545.nq.gz
│   ├── a5c40f3a7687bf044b9ebcb56c86ac51a1ac835c.nq.gz
│   ├── a8e48059bc7f6e643900f3cca21d53b9aaec90ff.nq.gz
│   ├── b22dac64bb16a705e825bd66944c5883b2bd3ac9.nq.gz
│   ├── bab02e627bd53ef7573c45d5fe735be116f617e6.nq.gz
│   ├── bae1bcd9a76eee1dc47975515408e4ae4fce0fb2.nq.gz
│   ├── c931c7acb24b1909c82b31c190883194cadfdd25.nq.gz
│   ├── d1fad63756b240a7b63afa6a9c5eff75769e0ffd.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f2f5869d6a673b563e9392c6506635fe9bbf0370.nq.gz
│   └── f4b11eda770e4606376a354d09a24093a2e35a19.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6e9931f7a1bb2387845f5d78d3ba312ae5585bfe.nq.gz
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

[joblib/joblib-spark](https://github.com/joblib/joblib-spark)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
