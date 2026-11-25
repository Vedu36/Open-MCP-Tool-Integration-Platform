# OpenMCP

OpenMCP is an open-source developer tool integration platform built on the
[Model Context Protocol](https://modelcontextprotocol.io/) (MCP). It is being
designed so AI agents can discover and use developer tools — filesystem, Git,
databases, and controlled terminal execution — through standardized, secure
contracts.

> **Status: bootstrap.** This repository currently contains the engineering
> foundation and documentation only. No MCP server, agent workflow, LLM
> integration, evaluation harness, or benchmark result is implemented yet.

## Why OpenMCP

AI agents become useful when they can act on real development environments, but
direct access to files, repositories, databases, and shells is risky. OpenMCP is
designed to provide a small, inspectable layer that will make those capabilities:

- **Discoverable** — tools will advertise schemas, capabilities, and risk levels.
- **Standardized** — integrations will use MCP contracts instead of bespoke glue.
- **Secure** — access will be denied by default and mediated by explicit policy.
- **Observable** — every tool decision and invocation will be traceable.
- **Evaluable** — reliability and safety will be measured, not assumed.

## Planned capabilities

| Capability | Status |
| --- | --- |
| Repository bootstrap and engineering foundation | **Implemented** |
| Python package skeleton and tooling configuration | **Implemented** |
| OpenCode skills, agents, and slash commands | **Implemented** |
| MCP tool contract and schema validation | **Planned** |
| Read-only filesystem MCP server | **Planned** |
| Git inspection MCP server | **Planned** |
| Database query MCP server | **Planned** |
| Controlled terminal execution MCP server | **Planned** |
| Tool registry and discovery | **Planned** |
| LangGraph agent orchestration | **Planned** |
| Local inference through Ollama | **Planned** |
| Langfuse observability | **Planned** |
| Evaluation harness | **Planned** |
| Benchmarks | **Methodology only; no results** |

Planned functionality is described in `ARCHITECTURE.md` and `ROADMAP.md`.
Nothing in this repository should be treated as production-ready.

## Quick start

Prerequisites:

- Python 3.11 or newer
- [uv](https://docs.astral.sh/uv/)
- Git

```sh
uv sync
uv run pytest
uv run ruff check .
uv run mypy src
```

There is no CLI or runnable MCP server yet. The current package only verifies
that the import path and tooling work.

## Repository layout

```text
.
├── .opencode/          # OpenCode skills, agents, commands, and policy
├── benchmarks/         # Benchmark workspace and methodology notes
├── docs/               # Documentation index
├── src/openmcp/        # Python package (bootstrap only)
├── tests/              # Automated tests
├── .env.example        # Local environment placeholders; no secrets
├── .gitignore          # Ignored local, generated, and credential files
├── .python-version     # Development interpreter pin
├── AGENTS.md           # Operating contract for coding agents
├── ARCHITECTURE.md     # System design and component boundaries
├── EVALUATION.md       # Evaluation strategy and success criteria
├── LICENSE             # Apache-2.0
├── METRICS.md          # Metrics and benchmarking methodology
├── README.md           # Project overview
├── ROADMAP.md          # Phased implementation plan
├── pyproject.toml      # Project metadata and tooling configuration
└── uv.lock             # Reproducible dependency resolution
```

## Documentation

- [Architecture](ARCHITECTURE.md)
- [Roadmap](ROADMAP.md)
- [Metrics and benchmarking](METRICS.md)
- [Evaluation strategy](EVALUATION.md)
- [Documentation index](docs/README.md)

## Development principles

- Free and open-source stack only; no paid APIs or mandatory cloud services.
- Local-first inference through Ollama when LLM integration begins.
- Security and observability are design inputs, not later additions.
- Small, independently testable changes with explicit acceptance criteria.
- No performance claims without reproducible measurements.

See `AGENTS.md` for the full engineering and agentic coding contract.

## License

Apache License 2.0. See [LICENSE](LICENSE).
