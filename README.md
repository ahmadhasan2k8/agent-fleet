# Claude Agent Fleet 🤖

Specialized AI agents for Claude Code that bring domain expertise to your development workflow.

## What is this?

A collection of 8 expert agents that Claude Code can automatically delegate tasks to based on your needs. Instead of general responses, you get specialized expertise from domain experts.

## 🚀 Quick Setup

1. **Install required MCP servers:**
```bash
# Sequential thinking (required for complex analysis)
npx @modelcontextprotocol/create-server sequential-thinking

# Memory management (optional but recommended)  
npx @modelcontextprotocol/create-server memory

# File system tools (optional but recommended)
npx @modelcontextprotocol/create-server filesystem
```

2. **Install the agents:**
```bash
git clone https://github.com/ahmadhasan2k8/agent-fleet.git
cp -r agent-fleet/.claude ~/.claude
```

3. **Configure Claude Code** to use the MCP servers (follow [Claude Code MCP setup docs](https://docs.anthropic.com/en/docs/claude-code/mcp))

That's it! Claude Code will automatically discover and use the agents.

## 🤖 Available Agents

- **Product Research Manager** - Market research, competitive analysis, user research
- **Cloud Infrastructure Architect** - AWS/Azure, containerization, DevOps  
- **Data Architecture Specialist** - Data platforms, ETL pipelines, warehousing
- **AI/ML Systems Engineer** - Model deployment, MLOps, production AI
- **Vision AI Architect** - Computer vision, 3D reconstruction, neural rendering
- **Agent Protocol Architect** - Multi-agent protocols (MCP, ACP), orchestration systems
- **Rapid Prototyping Engineer** - MVPs, proof of concepts, quick demos
- **Jetson Edge AI Engineer** - NVIDIA Jetson deployment, TensorRT optimization, edge AI

## 💡 How to Use

### Automatic Activation
Just describe what you need - Claude Code will automatically pick the right agent:

```
"Analyze the competitive landscape for AI code review tools"
→ Activates Product Research Manager

"I need to deploy a 70B parameter model with low latency"  
→ Activates AI/ML Systems Engineer

"Design a real-time data pipeline for user events"
→ Activates Data Architecture Specialist

"How do I optimize my model for Jetson Xavier?"
→ Activates Jetson Edge AI Engineer
```

### Manual Selection
You can also explicitly request an agent:

```
"Use the rapid-prototyping-engineer to build a WebRTC chat demo"
"Have the cloud-infrastructure-architect review my AWS setup"
```

## 📋 Usage Examples

### Market Research
**Input:** "I'm building an AI-powered code review tool. What's the market opportunity?"

**Agent Response:**
- Competitive analysis (GitHub Copilot, DeepCode, Sonar)
- Market size: $2.8B TAM, $400M SAM 
- User personas: Enterprise dev teams, security-focused orgs
- Pricing benchmarks: $12-50/developer/month
- Go-to-market recommendations

### Infrastructure Design  
**Input:** "Design a scalable architecture for 1M+ daily active users"

**Agent Response:**
- Auto-scaling container orchestration (EKS/AKS)
- CDN + load balancing strategy  
- Database sharding approach
- Monitoring and observability stack
- Cost optimization recommendations

### ML System Architecture
**Input:** "How do I serve a transformer model with <100ms latency?"

**Agent Response:**
- Model optimization (ONNX, TensorRT, quantization)
- Serving infrastructure (TorchServe, Triton)
- Caching strategies and batching
- Monitoring and A/B testing setup
- Scaling and cost analysis

### Rapid Prototyping
**Input:** "Build a proof of concept for real-time collaborative editing"

**Agent Response:**
- Technology stack recommendation (WebRTC, Socket.io)
- MVP feature breakdown
- Working code implementation
- Demo deployment strategy
- Path to production scaling

### Edge AI Deployment
**Input:** "Deploy YOLOv8 on Jetson Orin with 30 FPS performance"

**Agent Response:**
- TensorRT optimization pipeline (FP16/INT8 quantization)
- Container setup with CUDA and DeepStream
- Memory and power optimization strategies
- Real-time performance profiling
- Production deployment checklist

## 🔧 Customization

Want to modify an agent? Edit the files in `~/.claude/agents/`:

```yaml
---
name: your-custom-agent
description: When to use this agent
tools: [available tools]
model: sonnet
color: blue
---

Your agent instructions here...
```

## 🤝 Contributing

Found an issue or want to add an agent? Open an issue or PR!

---

**Transform Claude Code into a specialized AI team.** Each agent brings years of domain expertise to your fingertips. 🚀