# Repolex Knowledge Graph of epage/toml-test-rs

RDF knowledge graph data for [epage/toml-test-rs](https://github.com/epage/toml-test-rs), parsed by [repolex](https://repolex.ai).

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
rlex download epage/toml-test-rs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 45614df176dc8006f6517c74d738fc7f8c5a5c19
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 45614df176dc8006f6517c74d738fc7f8c5a5c19.nq.gz
│   └── repolex
│       └── 45614df176dc8006f6517c74d738fc7f8c5a5c19
│           └── chunk-001.nq.gz
├── blob
│   ├── 116e02f5914541d617ec336b758e89b9989e4121.nq.gz
│   ├── 1d4c5dc66f4e229b407587965d09da9816e06eac.nq.gz
│   ├── 1e29c7cf944fee8d0d11a0b516b968d03c1fb8a0.nq.gz
│   ├── 21bb7a03dd0f58ff4e05a8ab58e820f970289849.nq.gz
│   ├── 2e12bb4528ff834be14c8238324c9a1323e39018.nq.gz
│   ├── 352ef371bff0172765050ee193a127398fcdea83.nq.gz
│   ├── 4211ae3842810ba7207dfc2148a5354e28276bda.nq.gz
│   ├── 4b85b4dcda2b41f304efcbc154efbecd5c8346f7.nq.gz
│   ├── 5d48e0c474ab4c37c35d3c6066279225167c7b3b.nq.gz
│   ├── 68db968e9b57462fe451da882344f40ba07fe761.nq.gz
│   ├── 76405968525ef33fc6f16c8233602515301fbf4e.nq.gz
│   ├── 79020a304dfec30b8cad9c74cb37769284cd6a49.nq.gz
│   ├── 7b55a3d9f5ae236cc6134ecba00925a7526498ee.nq.gz
│   ├── 7d5dfe6325539d8755213ac5c4023171d0bd6b73.nq.gz
│   ├── 827e52e763d7e25b0f70189b8592b4d182722a46.nq.gz
│   ├── 8679384b18a1585269489e056ccd8fb2cf0d236f.nq.gz
│   ├── 8e58d9ec097c0d0f548b385b0850e743c0cf00fa.nq.gz
│   ├── 8f71f43fee3f78649d238238cbde51e6d7055c82.nq.gz
│   ├── a2d01088b6ce55e837a6d193943580f978fb2d2e.nq.gz
│   ├── a49a42109412b71540db4284db85aa1b407e8051.nq.gz
│   ├── a88074db192b85040870a7dc67d3d8fb679bf25f.nq.gz
│   ├── a8bf0be94d6e0b06fb0fcadc9bd645d287765c75.nq.gz
│   ├── a93094efe4d86724a79c158cbad6ddc933b415d4.nq.gz
│   ├── aa6d7d089e6315364426bfbc97277f762f1ee118.nq.gz
│   ├── ac4030090ac8b29bd727bce8f07d6a35af1e108f.nq.gz
│   ├── ae22a04176d0f8fc0a1bc1bcc05b715913e60611.nq.gz
│   ├── b703a7958fde6e7691e60579aefdf2e9a6194bbb.nq.gz
│   ├── c2417719675f6cb06a055eab7df0fc508ba1711c.nq.gz
│   ├── cdd2a441e435d93f1d890e31ea662db593e09c90.nq.gz
│   ├── d5c6eee60fbd3f3f1f544c4fb401db9d32c3be6b.nq.gz
│   ├── e32d37eec746979f3cb9d810dd0b020849f9d13f.nq.gz
│   ├── e7a50fbb3c3954e45314a8755ad49cfd45251e64.nq.gz
│   ├── eb5a316cbd195d26e3f768c7dd8e1b47299e17f8.nq.gz
│   ├── ee5ae89b3167c711c59f22a03e14f039a72e12cc.nq.gz
│   └── f0001f2e8cd1e78889945b4ff3e7b9bc680ef17f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 45614df176dc8006f6517c74d738fc7f8c5a5c19.nq.gz
├── filetree
│   └── 45614df176dc8006f6517c74d738fc7f8c5a5c19.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 45 files
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

[epage/toml-test-rs](https://github.com/epage/toml-test-rs)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
