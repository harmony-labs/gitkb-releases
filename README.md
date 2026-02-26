# GitKB

Git-native knowledge base with AI-powered code intelligence.

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

GitKB stores documents as markdown files with YAML frontmatter in a `.kb/` directory inside your git repo. A local SQLite index provides fast queries, full-text search, and graph traversal — but the files on disk are always the source of truth. If the database is ever lost, `git kb reindex` rebuilds it from files.

Documents are connected through a knowledge graph: tasks implement specs, incidents reference fixes, code symbols link to documentation. Wikilinks (`[[slug]]`) in your markdown automatically create graph edges.

For AI agents, GitKB provides an MCP server with 36 tools — document CRUD, graph queries, code intelligence, semantic search — giving agents structured, persistent context that survives session restarts.

## Links

- **Protocol spec:** [gitkb.org](https://gitkb.org) — open protocol specification
- **Product & docs:** [gitkb.com](https://gitkb.com) — documentation, guides, and cloud platform
- **Community:** [discord.gitkb.com](https://discord.gitkb.com)

## License

The GitKB CLI binary is distributed under the [Business Source License 1.1](LICENSE). This means:

- **You can use it** for any purpose, including commercial projects
- **You can read and audit** the source code
- **You can submit patches** and bugfixes
- **You cannot** use the source to build a competing managed service
- **After 3 years**, each version converts to MIT — fully open source

The [GitKB protocol specification](https://gitkb.org) is open. The `gitkb-types` and `gitkb-parser` crates are MIT-licensed on [crates.io](https://crates.io) for building extensions and packs. All built-in language packs are MIT.

Built by [Harmony Labs](https://harmony-labs.ai).
