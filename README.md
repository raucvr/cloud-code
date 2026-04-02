# Cloud Code

A local coding-agent CLI implemented in Rust and Python, inspired by Claude Code.

## Features

- Interactive REPL and one-shot prompt execution
- Built-in workspace tools: shell, file read/write/edit, search, web fetch/search, todo, notebook
- Slash commands: status, compact, config, diff, export, session, version
- Local agent and skill discovery
- Plugin system with hook pipeline
- OAuth login and model/provider selection
- MCP (Model Context Protocol) support
- Workspace-aware config loading (`CLAW.md`, permissions, plugin settings)

## Project Structure

```
.
├── src/          # Python source
├── rust/         # Rust workspace
│   ├── crates/api/         # API client + streaming
│   ├── crates/runtime/     # Session, config, MCP, prompt
│   ├── crates/claw-cli/    # Interactive CLI binary
│   ├── crates/tools/       # Built-in tool specs
│   ├── crates/commands/    # Slash command registry
│   ├── crates/plugins/     # Plugin system
│   ├── crates/lsp/         # LSP client integration
│   └── crates/server/      # HTTP/SSE server
└── tests/        # Verification tests
```

## Quick Start

### Prerequisites

- Rust stable toolchain
- Python 3.x

### Authentication

```bash
export ANTHROPIC_API_KEY="your-key"
```

### Build & Run (Rust)

```bash
cd rust
cargo build --release
./target/release/claw
./target/release/claw prompt "summarize this workspace"
```

### Run (Python)

```bash
python3 -m src.main summary
python3 -m src.main manifest
python3 -m unittest discover -s tests -v
```

## License

See the repository root for licensing details.
