# Repolex Knowledge Graph of dask/dask-sphinx-theme

RDF knowledge graph data for [dask/dask-sphinx-theme](https://github.com/dask/dask-sphinx-theme), parsed by [repolex](https://repolex.ai).

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
rlex download dask/dask-sphinx-theme
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0ac5a5fc37faaeef92d8c27aea1d058489e857c9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0ac5a5fc37faaeef92d8c27aea1d058489e857c9
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b281e52d166f1686acffcacc50b4ca3fd6c072d.nq.gz
│   ├── 107fed0414a2a279fd8b0e0e728afec871093647.nq.gz
│   ├── 185c634232c5613be9b2cf91760149e91d7e2a06.nq.gz
│   ├── 1f08f0bba69a57b1caec330ed9130fae48aa8422.nq.gz
│   ├── 207cad6dbb55de76cd6866f10f0d90560ff4bb71.nq.gz
│   ├── 2119f51099bf37e4fdb6071dce9f451ea44c62dd.nq.gz
│   ├── 22b7fd1e4624b2c71560b17fc257a03cded7fbf0.nq.gz
│   ├── 26581e072b3f34b3d51ad88e4b6dbc28b5c94d5a.nq.gz
│   ├── 2935df53bae779288a1ebfc617d511ec852edbab.nq.gz
│   ├── 2ebeebe9ba7b574cfd6d13467a9ea643170cdb95.nq.gz
│   ├── 362beab531cf9a686e113fe9e49857e3d324b551.nq.gz
│   ├── 37bf6bd875c5f3effa10986a270790c02b21e3fb.nq.gz
│   ├── 39f5c2771d347a59137d4ba36e8187f4d9858064.nq.gz
│   ├── 3a66c5473ab1f43d75a79d447d79222ccac7750e.nq.gz
│   ├── 415e09d7726303e587a64ff8797b0c682a18190f.nq.gz
│   ├── 693b7f693d38cbadf99607a487468c67370b97e7.nq.gz
│   ├── 6efb773075b992f7a717451390452cbcfdbf112a.nq.gz
│   ├── 728529eb2cdc5f25501af61275d6a7f3897cac45.nq.gz
│   ├── 779d138362147b823a15a623f0c8c25a76eb5a5b.nq.gz
│   ├── 7d95d51af1fb073a9af50568e67216d44a2da25c.nq.gz
│   ├── 8477d2fce464e72f72bb6c2fdb62324c4f7e158e.nq.gz
│   ├── 89696a9601154517af1e5b0eca07d43fb341ebcc.nq.gz
│   ├── 9f1c57986bedf0ff88fd2cc7258ad71fb394bd47.nq.gz
│   ├── b11dafac2f30604d47ce921685bc7ddba5987944.nq.gz
│   ├── b2b1d8ec7d6678174a41928545f6053dffe2ab04.nq.gz
│   ├── b4cd1d6c7c66ac52c492f9722e069466106d62fb.nq.gz
│   ├── b50c24dc36e03e5913494cedd5afc4f18c13f803.nq.gz
│   ├── bb558a004db612740cc088515620a6a95270b996.nq.gz
│   ├── bc574e79af7043be7ca13a167790d3e25af8984d.nq.gz
│   ├── bf68534f5f0479f61690fa196d3fb0c31e9dfcd9.nq.gz
│   ├── cfdf9dc4b02040f5c9fe3f083f60e84aa7e37df4.nq.gz
│   ├── e4689ca96ba6a7df8aea72b21ee87a01a6dba1d6.nq.gz
│   ├── e6eadce4d26a93431dcb21885932bd8544cf49c5.nq.gz
│   └── f94f35fc5be9ade227d1db6b4bdf0824e0570c30.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0ac5a5fc37faaeef92d8c27aea1d058489e857c9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 42 files
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

[dask/dask-sphinx-theme](https://github.com/dask/dask-sphinx-theme)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
