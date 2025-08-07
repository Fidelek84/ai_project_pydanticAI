## Python Local AI Agent
FastAPI AI agent with web search via SearXNG, compatible with Open WebUI and OpenAI-like LLMs (Ollama, OpenAI, etc.).

### Features
Conversation history (Supabase)
Web search (SearXNG)
Bearer token auth
Docker support with local-ai network
OpenAI-compatible API

### Prerequisites
Python 3.11+
Supabase project
SearXNG instance
Ollama or OpenAI API access

### Installation
git clone git@github.com:Fidelek84/ai_project_pydanticAI.git
cd ai_project_pydanticAI/python-local-ai-agent
python -m venv venv
# Activate venv:
# Linux/macOS: source venv/bin/activate
# Windows: venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env
# Edit .env to set your API URLs, keys, bearer token, etc.


### Database Setup (if not done already)
Run this SQL in Supabase:

CREATE EXTENSION IF NOT EXISTS pgcrypto;
CREATE TABLE n8n_chat_histories (
  id uuid DEFAULT gen_random_uuid() PRIMARY KEY,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP,
  session_id TEXT NOT NULL,
  message JSONB NOT NULL
);
CREATE INDEX idx_messages_session_id ON n8n_chat_histories(session_id);
CREATE INDEX idx_messages_created_at ON n8n_chat_histories(created_at);


### Running the Agent
source venv/bin/activate  # or venv\Scripts\activate on Windows
python main.py
API at: http://localhost:8055


### Docker (connected to local-ai network)
docker compose -p localai up -d --build python-local-ai-agent
Make sure your main local-ai stack is running and .env is properly configured.


### API Usage
Send chat to POST /invoke-python-agent with bearer token:

curl -X POST http://localhost:8055/invoke-python-agent \
  -H "Authorization: Bearer YOUR_BEARER_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"chatInput":"What is new in AI?","sessionId":"user-123"}'
Demo
Run openai_compatible_demo.py inside the venv to test OpenAI and Ollama integration.


### Troubleshooting
Check bearer token format
Confirm Supabase and SearXNG are running and reachable
Ensure Ollama server is running with your model


### Development
Edit main.py to customize behavior, add new tools with @agent.tool, update dependencies as needed.