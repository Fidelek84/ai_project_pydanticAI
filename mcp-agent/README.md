## Pydantic AI MCP Agent - Tool Integration Framework
Build AI agents that connect to Model Context Protocol (MCP) servers, enabling LLMs to access external tools through a standard interface using Pydantic AI.

### Quick Start
1. Copy mcp_client.py to your project.
2. Install dependencies:
pip install pydantic-ai mcp
3. Create an mcp_config.json like Claude Desktop’s config.
4. Create your agent:

import mcp_client
from pydantic_ai import Agent

async def get_pydantic_ai_agent():
    client = mcp_client.MCPClient()
    client.load_servers("mcp_config.json")
    tools = await client.start()
    return client, Agent(model='your-llm-here', tools=tools)


### Features
MCP-compatible tool integration
Dynamic discovery and conversion of MCP tools
CLI and FastAPI endpoint support
Conversation history with Supabase
Docker deployment for Live Agent Studio


### How It Works
Configure MCP servers in mcp_config.json
Connect to servers via stdio
Discover and convert tools
Initialize Pydantic AI agent with tools
Run agent to handle user input and call tools


### Prerequisites
Python 3.9+
Node.js (for MCP servers)
OpenAI API key or compatible provider (like Ollama)


### Setup
Create and activate a virtual environment
Install dependencies (pip install -r requirements.txt)
Set environment variables (PROVIDER, LLM_API_KEY, etc.)
Configure MCP servers in mcp_config.json
Run CLI app:
python pydantic_mcp_agent.py


### Extending
Add more MCP servers
Create custom tools
Customize agent configuration
Add memory features like Mem0


### Live Agent Studio
Set variables in studio-integration-version/.env
Run API server:
python pydantic_mcp_agent_endpoint.py
Or deploy via Docker


### Supabase Setup
Create a project and messages table for conversation data storage.


### Learn More
MCP: https://github.com/modelcontextprotocol/mcp
Pydantic AI: https://github.com/pydantic/pydantic-ai
Supabase: https://supabase.com/docs
FastAPI: https://fastapi.tiangolo.com/