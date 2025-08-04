# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## High-Level Architecture

This repository provides a specialized agent framework for Claude Code, extending its capabilities through domain-specific expert agents. The architecture follows a hub-and-spoke model where Claude Code can delegate complex tasks to specialized sub-agents.

### Agent System Design

The agent system is organized around **specialized expert agents** that complement Claude Code's general capabilities:

1. **Agent Definition Framework**: Each agent is defined using YAML frontmatter with:
   - `name`: Unique identifier for the agent
   - `description`: When to use this agent with usage examples
   - `tools`: Available MCP tools and native Claude Code functions
   - `model`: Claude model variant (typically sonnet)
   - `color`: Terminal UI color coding

2. **Tool Access Patterns**: All agents inherit the full Claude Code toolset including:
   - MCP tools (sequential-thinking, filesystem, memory, github)
   - Native tools (Glob, Grep, LS, Read, WebFetch, TodoWrite, WebSearch)
   - Domain-specific tool combinations optimized per agent role

3. **Agent Specialization Domains**:
   - **Product Strategy**: `product-research-manager` - Market research, competitive analysis, user research
   - **Infrastructure**: `cloud-infrastructure-architect`, `data-architecture-specialist` - System design and data platforms
   - **AI/ML**: `ai-ml-systems-engineer`, `vision-ai-architect` - ML systems and computer vision
   - **Integration**: `mcp-integration-architect` - MCP protocol and agent orchestration
   - **Development**: `rapid-prototyping-engineer` - MVP and prototype development

### Task Delegation Patterns

Claude Code delegates to agents based on:
- **Domain Expertise Match**: Technical domain alignment with agent specialization
- **Complexity Threshold**: Multi-step processes requiring systematic thinking
- **Tool Requirements**: Need for specialized tool combinations (e.g., sequential-thinking for complex analysis)

### MCP Integration Architecture

The framework leverages MCP (Model Context Protocol) for:
- **Sequential Thinking**: Complex multi-step analysis and planning
- **Memory Management**: Cross-session context and knowledge persistence
- **Filesystem Operations**: Enhanced file manipulation and project management
- **GitHub Integration**: Repository management and collaboration workflows

## Agent Configuration

### Agent File Structure
```
.claude/
├── agents/
│   ├── {agent-name}.md       # Agent definition with YAML frontmatter
│   └── ...
└── settings.local.json       # MCP permissions and configuration
```

### Permission Model
The `settings.local.json` configures MCP tool permissions:
- `allow`: Explicitly permitted MCP tools
- `deny`: Blocked MCP tools (security boundary)

### Agent Activation
Agents are activated through Claude Code's Task tool:
```
I'll use the {agent-name} agent to {specific-capability}
```

## Development Workflow

### Working with Agents
1. **Agent Selection**: Choose appropriate agent based on domain expertise requirements
2. **Task Specification**: Define clear objectives and success criteria
3. **Tool Coordination**: Agents automatically select optimal tool combinations
4. **Result Integration**: Agents return structured outputs for main Claude Code session

### Adding New Agents
1. Create agent definition in `.claude/agents/{name}.md`
2. Define specialization domain and tool requirements
3. Include usage examples with context commentary
4. Configure MCP permissions if new tools required

### Agent Communication Patterns
- **Synchronous**: Direct task delegation with immediate response
- **Context Preservation**: Agents maintain awareness of main session context
- **Tool Sharing**: All agents share the same comprehensive toolset
- **Result Formatting**: Structured outputs optimized for Claude Code integration

## System Requirements

- Claude Code with MCP support
- Sequential-thinking MCP server (required for complex analysis)
- File system access for agent definitions
- GitHub integration for repository operations (optional)

The agent framework extends Claude Code's capabilities while maintaining its core interaction patterns and user experience.