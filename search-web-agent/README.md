# Web Search Agent with Pydantic AI

This repository contains a Python script (`web_search_agent.py`) that leverages large language models (LLMs) and web search capabilities to answer user questions. It uses `search-web-agent` for agent functionality and integrates with Ollama for local LLM inference and Brave Search API for web queries.

## Setup and Installation

1.  **Navigate to the project directory:**
    ```bash
    cd search-web-agent
    ```

2.  **Create a Python virtual environment:**
    ```bash
    python -m venv .venv
    ```

3.  **Activate the virtual environment:**
    *   **On Windows (Command Prompt):**
        ```cmd
        .venv\Scripts\activate
        ```
    *   **On Windows (PowerShell):**
        ```powershell
        .venv\Scripts\activate
        ```
    *   **On Linux/macOS:**
        ```bash
        source .venv/bin/activate
        ```

4.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt --break-system-packages
    ```
    (The `--break-system-packages` flag might be necessary on some Linux distributions like WSL-Ubuntu if you encounter "externally-managed-environment" errors.)

## Configuration

### LLM Model (Ollama)

This agent is configured to use a local Ollama instance.

1.  **Install Ollama:** Download and install Ollama from [ollama.com](https://ollama.com/).
2.  **Pull a compatible model:** You need a model that supports tool use. `llama3` or `mixtral` are recommended.
    ```bash
    ollama pull llama3.2:1b
    ```
    (Replace `llama3.2:1b` with your preferred model if different.)

3.  **Set the `LLM_MODEL` environment variable:**
    *   **On Windows (PowerShell):**
        ```powershell
        $env:LLM_MODEL="llama3.2:1b"
        ```
    *   **On Windows (Command Prompt):**
        ```cmd
        set LLM_MODEL=llama3.2:1b
        ```
    *   **On Linux/macOS:**
        ```bash
        export LLM_MODEL="llama3.2:1b"
        ```
    (Ensure this variable is set in the same terminal session where you run the script.)

### Brave Search API Key

The script uses the Brave Search API for web queries.

1.  **Obtain a Brave Search API Key:** Sign up and get your API key from the Brave Search API documentation.
2.  **Set the `BRAVE_API_KEY` environment variable:**
    *   Create a `.env` file in the `search-web-agent` directory with the following content:
        ```
        BRAVE_API_KEY='your_brave_api_key_here'
        ```
        Replace `'your_brave_api_key_here'` with your actual Brave Search API key.

## Running the Script

Once the environment is set up and configured, you can run the web search agent:

```bash
python web_search_agent.py
```

The script will execute the web search query defined within `main()` function and print the results.
