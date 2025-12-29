# Libre Google Workspace Agents

**An OpenSource Model Context Protocol (MCP) Server ecosystem for comprehensive agentic AI access to Google Workspace**

## Vision

Build a collaborative community-driven project that provides AI agents with comprehensive, secure, and well-architected access to all Google Workspace capabilities through a router-like MCP architecture.

## Project Ontology

### Core Concept: "Libre" Philosophy
- **Libre** (Spanish/French: "free") emphasizes freedom and openness
- Open source, community-driven development
- Transparent security practices
- Educational resources for AI agent development
- Best practices for human-AI collaboration

### Architecture: Router-like MCP Server
```
┌─────────────────────────────────────────────────────────────┐
│         Libre Google Workspace MCP Router                   │
├─────────────────────────────────────────────────────────────┤
│  Authentication Layer (Service Accounts, OAuth, ADC)        │
├─────────────────────────────────────────────────────────────┤
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐   │
│  │  Drive   │  │  Sheets  │  │  Docs    │  │  Gmail   │   │
│  │  MCP     │  │  MCP     │  │  MCP     │  │  MCP     │   │
│  └──────────┘  └──────────┘  └──────────┘  └──────────┘   │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐   │
│  │ Calendar │  │  Meet    │  │  Chat    │  │  Forms   │   │
│  │  MCP     │  │  MCP     │  │  MCP     │  │  MCP     │   │
│  └──────────┘  └──────────┘  └──────────┘  └──────────┘   │
└─────────────────────────────────────────────────────────────┘
```

### Monorepo Structure with Git Worktrees

This repository uses a monorepo architecture with Git worktrees for parallel development:

```
libre-google-workspace-agents/
├── main/                          # Main integration branch worktree
├── gcp-mcp-testing/               # Service Account testing & validation
├── drive-mcp-server/              # Google Drive MCP implementation (future)
├── sheets-mcp-server/             # Google Sheets MCP implementation (future)
├── docs-mcp-server/               # Google Docs MCP implementation (future)
├── router-architecture/           # Core router implementation (future)
└── shared-infrastructure/         # Common utilities & auth (future)
```

## Current Phase: Foundation

### Active Worktree: `gcp-mcp-testing`
**Purpose**: Establish secure foundations for Google Cloud Platform Service Account management

**Scope**:
1. Service Account provisioning and security best practices
2. CRUD operation testing on Google Drive/Sheets
3. Comparison of authentication approaches (resource-level vs domain-wide delegation)
4. Documentation-as-code framework
5. Test automation patterns for AI agent development

**Why This Matters**:
- Security-first approach to AI agent access
- Evidence-based comparison of authentication patterns
- Reusable patterns for future MCP server implementations
- Clear documentation for community contributors

## Development Philosophy

### Multi-Agentic Software Development Lifecycle (SLDC)
This project serves as a reference implementation for:
- **Dialectic Synthesis**: Multiple AI agents exploring problem space from different perspectives
- **Parallel Development**: Git worktrees enable concurrent workstreams
- **Documentation-as-Code**: Living documentation that evolves with the codebase
- **Milestone-based Planning**: Feature-driven progress, not time-driven deadlines
- **Conventional Commits**: Rich commit messages with context and reasoning

### Git Worktree Strategy
```bash
# Example: Create new worktree for parallel development
git worktree add -b feature/drive-mcp-implementation drive-mcp-server

# Long descriptive branch names with context
git worktree add -b investigation/oauth2-vs-service-account-performance-comparison gcp-mcp-testing
```

## Project Milestones (Feature-Driven, Not Time-Driven)

### Milestone 1: Foundation & Security ✓ (In Progress)
- [x] Service Account authentication research
- [x] Security comparison (resource-level vs DwD)
- [x] Phase 1 verification of existing MCP servers
- [ ] Comprehensive testing framework
- [ ] Documentation infrastructure
- [ ] GitHub project structure with Issues/Milestones

### Milestone 2: Google Sheets MCP Server
- [ ] Complete MCP server implementation
- [ ] Comprehensive test suite
- [ ] Performance benchmarking
- [ ] Security audit
- [ ] API documentation

### Milestone 3: Google Drive MCP Server
- [ ] File operations (CRUD)
- [ ] Folder management
- [ ] Sharing and permissions
- [ ] Search and metadata
- [ ] Integration tests with Sheets MCP

### Milestone 4: Router Architecture
- [ ] Central authentication management
- [ ] Request routing logic
- [ ] Error handling and fallbacks
- [ ] Load balancing considerations
- [ ] Observability and monitoring

### Milestone 5: Community & Documentation
- [ ] Contribution guidelines
- [ ] Architecture Decision Records (ADRs)
- [ ] Runbooks and operational guides
- [ ] Tutorial content
- [ ] Community forum setup

## Technology Stack

### Core Technologies
- **Language**: Python 3.11+
- **MCP Framework**: FastMCP / Standard MCP SDK
- **Authentication**: Google Cloud IAM (Service Accounts, OAuth 2.0, ADC)
- **APIs**: Google Workspace APIs (Drive, Sheets, Docs, Gmail, Calendar, etc.)
- **Version Control**: Git with worktrees
- **Documentation**: MkDocs Material / Docusaurus
- **Testing**: pytest, pytest-asyncio
- **CI/CD**: GitHub Actions
- **Project Management**: GitHub Projects v2

### Development Tools
- **AI Orchestration**: Claude Code, Claude Desktop
- **Package Management**: uv (fast Python package manager)
- **Code Quality**: ruff (linting), black (formatting), mypy (type checking)
- **Security**: safety (dependency scanning), bandit (security linting)

## Getting Started

### Prerequisites
- Python 3.11+
- Google Cloud Platform account
- Google Workspace admin access (for Service Account setup)
- Git 2.35+ (for worktree support)

### Quick Start
```bash
# Clone the repository
git clone https://github.com/sebastianmalcolm/libre-google-workspace-agents.git
cd libre-google-workspace-agents

# Setup development environment
./scripts/setup-dev-environment.sh

# Create a worktree for your work
git worktree add -b feature/your-feature-name your-worktree-dir

# Navigate to worktree and start developing
cd your-worktree-dir
```

## Contributing

We welcome contributions! This project is in early stages and we're establishing patterns for:
- Multi-agentic AI development workflows
- Security-first authentication patterns
- Comprehensive documentation practices
- Test-driven development for AI-integrated systems

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

## Project Naming Rationale

### Why "Libre" instead of "Open"?
- **Libre** emphasizes freedom (libre = free as in freedom)
- Avoids confusion with "open" (which can mean open vs closed)
- International flavor (Spanish/French) signals global community
- Philosophical alignment with FOSS (Free and Open Source Software) principles

### Why "Agents" instead of "MCP Servers"?
- **Agents** is more accessible to non-technical contributors
- Reflects the agentic AI use case
- "MCP Servers" is still accurate (in technical docs)
- Positions project at intersection of AI agents and Workspace APIs

### Why "Google Workspace" not "GCP"?
- **Google Workspace** is the end-user product suite
- GCP (Google Cloud Platform) is the infrastructure layer
- Project scope includes Workspace APIs (Drive, Sheets, Docs, Gmail, Calendar)
- GCP is a means (Service Accounts, IAM) to the Workspace end

## License

[MIT License](LICENSE) - This project is free and open source.

## Security

Security is paramount. See [SECURITY.md](SECURITY.md) for:
- Vulnerability reporting procedures
- Security best practices for Service Accounts
- Threat model documentation
- Audit log requirements

## Support

- **Issues**: [GitHub Issues](https://github.com/sebastianmalcolm/libre-google-workspace-agents/issues)
- **Discussions**: [GitHub Discussions](https://github.com/sebastianmalcolm/libre-google-workspace-agents/discussions)
- **Documentation**: [Project Wiki](https://github.com/sebastianmalcolm/libre-google-workspace-agents/wiki)

## Acknowledgments

- Built with [Claude Code](https://claude.ai/claude-code) and [Claude Opus 4.5](https://www.anthropic.com/claude/opus)
- Inspired by [xing5/mcp-google-sheets](https://github.com/xing5/mcp-google-sheets)
- Informed by [Google's Workspace API documentation](https://developers.google.com/workspace)
- Follows [Model Context Protocol](https://modelcontextprotocol.io) specification

---

**Status**: 🚧 In Active Development - Foundation Phase
**Contributors**: Sebastian Malcolm (@sebastianmalcolm), Claude AI Agents
**Last Updated**: 2025-12-29
