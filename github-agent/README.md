## Pydantic AI: GitHub Repo Analysis Agent
AI agent using Pydantic AI to analyze GitHub repos—fetch info, explore directories, and read files via GitHub API.

### Features
- Get repo info (size, description)
- Analyze directory structure
- Check file contents
- Supports OpenAI & OpenRouter models
- Use as API or CLI

### Requirements
Python 3.11+
GitHub Personal Access Token (for private repos)
OpenRouter API key

### Setup (Python)
#### Clone repo and enter folder:
git clone git@github.com:Fidelek84/ai_project_pydanticAI.git
cd ottomator-agents/pydantic-github-agent

#### Install dependencies:
pip install -r requirements.txt

#### Rename .env.example to .env and add your API keys:
GITHUB_TOKEN=your_token
OPEN_ROUTER_API_KEY=your_key
LLM_MODEL=deepseek/deepseek-chat


### Run
Start API server:
python github_agent_endpoint.py
Access at http://localhost:8001

Or run CLI:
python cli.py

#### Setup (Docker)
Clone and configure .env as above
Build and run:
docker build -t github-agent .
docker run -p 8001:8001 --env-file .env github-agent