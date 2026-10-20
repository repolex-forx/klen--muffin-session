# Repolex Knowledge Graph of klen/muffin-session

RDF knowledge graph data for [klen/muffin-session](https://github.com/klen/muffin-session), parsed by [repolex](https://repolex.ai).

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
rlex download klen/muffin-session
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7de23a03ce00b61ba9adf01436b392c39e2df680
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 7de23a03ce00b61ba9adf01436b392c39e2df680
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a6ee958310ca78a98bf4803c291d5898c7fd5b4.nq.gz
│   ├── 1cd68de52e1ad33e3548cb7d3525ae94c946344b.nq.gz
│   ├── 23c5c150f58bdd129447223d88288e859f8cccb1.nq.gz
│   ├── 3d3de9177b065ccd2b82e03a2cd70dd8b0e5323a.nq.gz
│   ├── 4a060cc8ce501e4a5b9157c2f5ed52285582dd60.nq.gz
│   ├── 5b96d8dc972a5b2152e932f97bcee8b8ee9dceb2.nq.gz
│   ├── 5f1d5686f3dc12105665875988bbe0b90d32c2bc.nq.gz
│   ├── 5f94f6d2a638b6cff0c8af2f40478b8f874bd41c.nq.gz
│   ├── 666ce2a519fd8f0c3599a11f968422b82612ca92.nq.gz
│   ├── 78df056a6afd6b2f7c5a8695635380a19f30acd9.nq.gz
│   ├── 7a3f07ab83552f47a8705fa5d22729a324a2f71a.nq.gz
│   ├── 8266cabce06efb1e50c31ce221a7c095f3233cc5.nq.gz
│   ├── 9072ae34323de98369469d29e1883b19e38e0f26.nq.gz
│   ├── 92bd5157a187982bc555b4bb399eab258726fd7e.nq.gz
│   ├── 9a564ea1169c3177834be2acd0c1ab0a7a44304a.nq.gz
│   ├── b1ec394bd935fd3d8cac8e97d2eab7a0c26337d7.nq.gz
│   ├── b24e39a590c1bf09a6b1e4a28a34d9cac1435e5e.nq.gz
│   ├── be18c273980280646a2aaa370950ae041a9ed695.nq.gz
│   ├── c877256871e48ccaae105ee1e335a00149a54794.nq.gz
│   ├── ce48f87110f5a00c4f3320f9ed0c8e630cb23daf.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e728d03676c20ba87a39556e60b642f5df17ebde.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 7de23a03ce00b61ba9adf01436b392c39e2df680.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 30 files
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

[klen/muffin-session](https://github.com/klen/muffin-session)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
