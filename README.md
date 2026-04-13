# Repolex Knowledge Graph of git-albertomarin/winpath

RDF knowledge graph data for [git-albertomarin/winpath](https://github.com/git-albertomarin/winpath), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download git-albertomarin/winpath
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1c717d83aeee942d7b7e842ff2bfe61053ac3fee
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 1c717d83aeee942d7b7e842ff2bfe61053ac3fee.nq.gz
│   └── repolex
│       └── 1c717d83aeee942d7b7e842ff2bfe61053ac3fee
│           └── chunk-001.nq.gz
├── blob
│   ├── 1bf0c22d623a9f46b7ce0d4da113c7df47224bbc.nq.gz
│   ├── 25dfea31be5e406243f90aa645267fb3f8dfea39.nq.gz
│   ├── 2f5304a32c021463ea5d85ee70d8e356acf02e3e.nq.gz
│   ├── 3f51a41cbae88bd49b70db2ee2f65a1b8bb129e4.nq.gz
│   ├── 45998b6ccc78286bac874552c8bd69a6b111bbb8.nq.gz
│   ├── 53da45b18ea6a84c8c0908f7c18eb888434abc65.nq.gz
│   ├── 8f739d6327fe5ac9125c7c0396d97528ff9b521a.nq.gz
│   ├── ac7a462beaeefa4490fd7c4234a702b161b1953c.nq.gz
│   ├── de69a78de29c086f26efaf664e20add50947266b.nq.gz
│   ├── e3cae2e4093bcc3949f8a9e2dd7397a4f85393eb.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1c717d83aeee942d7b7e842ff2bfe61053ac3fee.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
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

## Source repository

[git-albertomarin/winpath](https://github.com/git-albertomarin/winpath)

---
*Parsed on 2026-04-13 by [repolex](https://repolex.ai)*
