## Pydantic AI: Web Search Agent with Brave API
An advanced web search agent using Pydantic AI and Brave Search API with CLI and Streamlit UI. Supports OpenAI GPT or Ollama local models. Summarizes articles found via Brave API for concise answers.


### Setup
1. Clone repo and enter folder:
git clone https://github.com/Fidelek84/ai_project_pydanticAI/advanced-researcher
cd ai_project_pydanticAI/advanced-researcher

2. Install dependencies:
pip install -r requirements.txt

3. Rename .env.example to .env and add keys:
OPENAI_API_KEY=your_key (if using GPT)
BRAVE_API_KEY=your_brave_key
LLM_MODEL=your_model (e.g., gpt-4o, qwen2.5:32b)


### Usage
Run CLI (supports GPT or Ollama based on LLM_MODEL):
python web_search_agent.py

Run Streamlit UI (uses GPT for streaming):
streamlit run streamlit_ui.py

### Configuration
- Set LLM_MODEL for model choice (OpenAI or Ollama)
- Get Brave API key from Brave Search API
- Get OpenAI API key from OpenAI (optional)

### Troubleshooting
- Ensure Ollama server is running and model pulled
- Check API keys and Brave API quotas
- For Ollama models, ensure enough RAM or use smaller models