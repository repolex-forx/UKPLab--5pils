# Repolex Knowledge Graph of UKPLab/5pils

RDF knowledge graph data for [UKPLab/5pils](https://github.com/UKPLab/5pils), parsed by [repolex](https://repolex.ai).

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
rlex download UKPLab/5pils
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── acf672a20900f80e99f2d013aa2f30b7469fa180
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── acf672a20900f80e99f2d013aa2f30b7469fa180
│           └── chunk-001.nq.gz
├── blob
│   ├── 10fc3fc8c3d166c6ba49f25f94c60d7a53693e5b.nq.gz
│   ├── 154818962f43a6a91a2627f0e8bf8927b98bce78.nq.gz
│   ├── 1b76da98f607e13e009c398dcc9bc7ab9acf2b80.nq.gz
│   ├── 2adacd579078c49035b56a20a824aed6c9e5ed65.nq.gz
│   ├── 2bfc9610c5a2e355073ac1a2441ac5d3c54467c0.nq.gz
│   ├── 39268a6dbf7b163cd79a44219e30c7f22c6d62cb.nq.gz
│   ├── 48d1cf0715e16090d81810834101a96de57a452d.nq.gz
│   ├── 48d25da104d9e20be7dd775801190f6a48d07f77.nq.gz
│   ├── 5b8ff7a9b1c5009a95bc870413647a8f4a2795a4.nq.gz
│   ├── 5cbc69161af60c27eb1524e154e118dfe1a32df2.nq.gz
│   ├── 614cc74ae48802e8ae2f55b799f37f3bcf38753e.nq.gz
│   ├── 6cb922737a9158c39b4ea3d3ed56ab68e79bbc77.nq.gz
│   ├── 72e03d7de415d496d8d2f8912546e788491bd2e1.nq.gz
│   ├── 7716073ed524c13ade71497da56f25ce8573b23c.nq.gz
│   ├── 83ff659aa11533a6bb598abaf8746e4ebdac0663.nq.gz
│   ├── 89907937f6784bbc07ab441f30e31be59ca657f8.nq.gz
│   ├── 908ecded7c75e371434ddd19c53cb903f7766017.nq.gz
│   ├── 92661667c2ebfe28325014c9454da0b81113bdf5.nq.gz
│   ├── 938f7489507b751fd0920bce0b59c300c01fa6bf.nq.gz
│   ├── 94905b20704ef93a4f6d4ca5a670ba9356e63293.nq.gz
│   ├── 95feeb42974de14a6f2ca2a50e66c32311e3a46d.nq.gz
│   ├── a331a9cea9392db47cb6de868322926b1c3d1d7e.nq.gz
│   ├── a538efc06f4f981134e4528a01480ca6ddd16297.nq.gz
│   ├── ae856a5885c1a3d76b649a854d4ded251fee12e7.nq.gz
│   ├── b1688cb3989de20618ba88fb0fa0370d904ebd68.nq.gz
│   ├── b81eed2c0efbcaf5625d52540ddd2c9bb4b2d715.nq.gz
│   ├── ba04ba4f81f67a446a0880a13be2e3474dea547c.nq.gz
│   ├── cda20b036c02ce44f0b5e51b240ceceac3b6f0df.nq.gz
│   ├── d0c18d32420e4dbd0127d7b90c3f2af524b6b727.nq.gz
│   ├── d6e2e906cc9fb0734ffe52a5072b7996883e7cd0.nq.gz
│   ├── dee914ca2a5f64c69f70f9d06967b9e8f2873022.nq.gz
│   └── fea3a0796d541d630a24de3f0ce12edf5d0991ca.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── acf672a20900f80e99f2d013aa2f30b7469fa180.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 39 files
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

[UKPLab/5pils](https://github.com/UKPLab/5pils)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
