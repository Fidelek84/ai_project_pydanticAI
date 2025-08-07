## Pydantic AI with Langfuse Observability
A multi-agent system built with Pydantic AI and Langfuse for monitoring AI agents using OpenAI, OpenRouter, or Ollama LLMs.

### Key Components
- Main agent delegates tasks to specialized subagents (Airtable, Brave Search, Filesystem, GitHub, Slack, Firecrawl)
- Uses MCP servers for tools
- Langfuse tracks usage, performance, and conversation tracing

### Requirements
- Python 3.11+, Node.js, npm
- Langfuse cloud or self-hosted
- API keys for LLMs and services

### Setup
1. Clone repo and create virtual environment
2. Install dependencies (pip install -r requirements.txt)
3. Create and configure .env with API keys and settings
4. Setup Langfuse (cloud or self-hosted)
5. Run main agent:
python pydantic_ai_langfuse_agent.py
6. Or run simple examples in iterations/

### Viewing Observability
- Access traces on Langfuse dashboard (cloud or self-hosted)
- Inspect model calls, inputs/outputs, performance metrics

### Architecture
- AsyncExitStack manages MCP servers
- Subagents have defined expertise and prompts
- Primary agent orchestrates subagents dynamically