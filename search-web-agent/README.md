## Web Search Agent with Pydantic AI
A Python script (web_search_agent.py) that uses local Ollama LLM and Brave Search API to answer questions via search-web-agent.

## Setup
Go to the project folder: cd search-web-agent
Create and activate a Python virtual environment:
Windows (Cmd/PowerShell): .venv\Scripts\activate
Linux/macOS: source .venv/bin/activate
Install dependencies:
pip install -r requirements.txt --break-system-packages (if needed on Linux)

## Configuration
Ollama LLM:
Install Ollama from ollama.com , pull a model like llama3.2:1b with:
ollama pull llama3.2:1b
Set environment variable LLM_MODEL to your model name.
Brave Search API Key:
Get an API key from Brave Search and add it to a .env file as:
BRAVE_API_KEY='your_key_here'

## Run
Run the agent with:
python web_search_agent.py
It will perform a web search and display results.