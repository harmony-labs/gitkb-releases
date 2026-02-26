# GitKB

GitKB is a git-like distributed knowledge graph protocol with sparse sync and checkout semantics, enabling agents and their humans to work on all the world's knowledge — a few documents at a time.

GitKB gives AI coding agents persistent memory that survives session restarts — structured documents, a knowledge graph, and deep code understanding across 23+ languages. It works with Claude Code, Cursor, and any MCP-compatible editor.

## Why GitKB

- **Files are source of truth.** Documents are markdown files on disk. Read them with `cat`, version them with `git`, take them with you if you leave. Zero vendor lock-in.
- **Code intelligence built in.** Call graphs, impact analysis, dead code detection across 23+ languages. The only knowledge base that understands your code.
- **Single binary, zero dependencies.** No external database, no server to run. `git kb init` and you're working.
- **AI-native.** 36 MCP tools for deep integration with Claude Code, Cursor, and every MCP-compatible editor. Agents get structured context, not just text files.
- **Extensible via Packs.** Language packs for new programming languages. Context packs for project bootstrapping. Foundation packs for domain vocabulary. Extension packs for skills, hooks, and workflows. All through a marketplace.

## Install

### Quick install (macOS / Linux)

```bash
curl -fsSL https://raw.githubusercontent.com/harmony-labs/gitkb-releases/main/install.sh | bash
```

### Homebrew

```bash
brew install harmony-labs/tap/gitkb
```

### Cargo binstall

```bash
cargo binstall gitkb-cli
```

### Specific version

```bash
VERSION=0.1.0 curl -fsSL https://raw.githubusercontent.com/harmony-labs/gitkb-releases/main/install.sh | bash
```

## Quick Start

```bash
# Initialize a knowledge base in your project
git kb init

# Set up AI agent integration (Claude Code)
git kb init claude

# Create your first document
git kb create --type task --title "My first task"

# View your knowledge base
git kb board

# Index your code for intelligence features
git kb code index src/
```

## What You Can Do

```bash
# Knowledge management
git kb create         # Create documents (tasks, specs, incidents, notes, ADRs)
git kb board          # Kanban view of tasks
git kb search         # Full-text search across all documents
git kb graph          # Visualize document relationships

# Git-like workflow
git kb checkout       # Edit documents in your workspace
git kb commit         # Save changes
git kb diff           # See what changed
git kb stash          # Temporarily shelve work

# Code intelligence
git kb code index     # Index your codebase
git kb code callers   # Find who calls a function
git kb code impact    # Analyze blast radius of changes
git kb code dead      # Find unused code

# AI agent integration
git kb mcp            # Start MCP server for editor integration
```

## How It Works

GitKB is a distributed protocol — like git for knowledge. Every project gets a `.kb/` directory containing markdown documents with YAML frontmatter. These files are the source of truth: version them with git, read them with any editor, take them with you if you leave. A local index provides fast queries, full-text search, and graph traversal. If the index is ever lost, `git kb reindex` rebuilds it from files.

**Sparse sync** means agents and humans pull only the documents they need. A team of agents working across a 10,000-document knowledge base each maintains a lightweight working set — no full clone required. **Sparse checkout** means the workspace is an ephemeral editing surface: check out what you're working on, commit when done, clear when finished.

Documents connect through a knowledge graph. Tasks implement specs. Incidents reference fixes. Code symbols link to documentation. Wikilinks (`[[slug]]`) in your markdown automatically create graph edges, making the entire knowledge base traversable and queryable.

For AI agents, GitKB exposes an MCP server with 36+ tools — document CRUD, graph traversal, code intelligence (call graphs, impact analysis, dead code detection across 23+ languages), and semantic search. Agents get structured, persistent context that survives session restarts — not just a pile of text files.

## Links

- **Product & docs:** [gitkb.com](https://gitkb.com) — documentation, guides, and cloud platform
- **Community:** [discord.gitkb.com](https://discord.gitkb.com)

## License

The GitKB CLI binary is distributed under the [Business Source License 1.1](LICENSE). This means:

- **You can use it** for any purpose, including commercial projects (via the Additional Use Grant)
- **You can read and audit** the source code
- **You can submit patches** and bug fixes
- **You cannot** use the source to build a competing managed service
- **After 4 years**, each version automatically converts to an open-source license

Built by [GitKB, Inc.](https://gitkb.com)
