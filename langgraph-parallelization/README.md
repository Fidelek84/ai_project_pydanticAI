## Travel Planning Agent System
A multi-agent travel planner using Pydantic AI and LangGraph with an interactive Streamlit UI.

### Features
- Parallel agents for flights, hotels, activities
- Conversational UI with preferences for airlines, budget, amenities
- Real-time responses streamed via Streamlit
- Agents work concurrently and combine results into a full plan

### Architecture
- Info Gathering Agent: collects trip details
- Flight Agent: recommends flights
- Hotel Agent: suggests hotels
- Activity Agent: recommends activities
- Final Planner Agent: creates complete itinerary

### Setup
Clone repo and enter folder:
git clone git@github.com:Fidelek84/ai_project_pydanticAI.git
cd ai_project_pydanticAI/langgraph-parallelization

### Create and activate virtual environment:
- Windows:
python -m venv venv
venv\Scripts\activate

- Mac/Linux:
python3 -m venv venv
source venv/bin/activate

### Install dependencies:
pip install -r requirements.txt
Create .env file based on .env.example with your API keys.

### Run
Start Streamlit UI:
streamlit run streamlit_ui.py
Open the shown URL in your browser.

### Usage
- Set preferences in sidebar
- Enter travel request in chat (e.g., "Trip to Tokyo from Minneapolis, Jun 1-6, hotel max $300")
- Follow prompts for missing info
- Receive full travel plan with flights, hotels, activities

### Customize
- Edit agent prompts
- Add agents/tools for extra travel features
- Integrate real APIs

Built with Pydantic AI , LangGraph , and Streamlit .