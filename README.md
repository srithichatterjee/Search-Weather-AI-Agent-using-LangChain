# 🤖 Search + Weather AI Agent using LangChain

[![Live Demo](https://img.shields.io/badge/Live%20Demo-ClimateClue-brightgreen?style=for-the-badge&logo=render)](https://climateclue.onrender.com/)

A ReAct-based agentic AI assistant that combines **real-time web search** and **live weather lookups** in a clean Streamlit interface. Built with LangChain, Groq (LLaMA 3.3 70B), Tavily Search, and the Weatherstack API.

**🔗 Try it live → [climateclue.onrender.com](https://climateclue.onrender.com/)**

---

## What it does

You type a natural language query — like *"What's the weather in Tokyo and who won the last F1 race?"* — and the agent figures out which tools to use, in what order, and gives you a composed answer. No hardcoded logic. Just the model reasoning through it.

---

## Tech Stack

| Layer | Tool |
|---|---|
| LLM | Groq — `llama-3.3-70b-versatile` |
| Agent Framework | LangChain ReAct (`create_react_agent`) |
| Web Search | Tavily Search API |
| Weather | Weatherstack API |
| UI | Streamlit |
| Env Management | `python-dotenv` |

---

## Project Structure

```
Search-Weather-AI-Agent-using-LangChain/
├── app.py              # Main Streamlit app with agent setup
├── main.py             # Alternate entry point / experimentation
├── research/           # Notebooks and exploration work
├── requirements.txt    # Dependencies
├── .gitignore
└── README.md
```

---

## 🚀 Live Demo

**[climateclue.onrender.com](https://climateclue.onrender.com/)** — deployed on Render

> Note: Render free tier spins down after inactivity, so the first load might take ~30 seconds to wake up.

---

## Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/srithichatterjee/Search-Weather-AI-Agent-using-LangChain.git
cd Search-Weather-AI-Agent-using-LangChain
```

### 2. Create and activate a conda environment

```bash
conda create -n langagent python=3.11 -y
conda activate langagent
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Set up environment variables

Create a `.env` file in the root directory:

```env
GROQ_API_KEY=your_groq_api_key
WEATHERSTACK_API_KEY=your_weatherstack_api_key
TAVILY_API_KEY=your_tavily_api_key
```

You can get these keys from:
- [Groq Console](https://console.groq.com/)
- [Weatherstack](https://weatherstack.com/)
- [Tavily](https://tavily.com/)

### 5. Run the app

```bash
streamlit run app.py
```

---

## How it works

The agent uses the **ReAct (Reasoning + Acting)** pattern — it thinks step by step, decides which tool to call, observes the result, and repeats until it has enough to answer.

```
User Query
    ↓
ReAct Agent (LLaMA 3.3 70B via Groq)
    ├── Tool: TavilySearchResults  → live web search
    └── Tool: get_weather_data     → Weatherstack API
    ↓
Final composed response → Streamlit UI
```

**Example queries you can try:**
- `"What's the weather in Hyderabad and what are the latest AI news?"  `
- `"Tell me about LangChain and weather in San Francisco"`
- `"Find the capital of Japan and current temperature there"`

---

## API Keys — quick guide

| Key | Where to get it | Free tier? |
|---|---|---|
| `GROQ_API_KEY` | [console.groq.com](https://console.groq.com/) | Yes |
| `WEATHERSTACK_API_KEY` | [weatherstack.com](https://weatherstack.com/) | Yes (250 req/month) |
| `TAVILY_API_KEY` | [tavily.com](https://tavily.com/) | Yes (1000 req/month) |

---

## Requirements

```
langchain
langchain-groq
langchain-community
streamlit
python-dotenv
requests
certifi
tavily-python
```

Install all at once with `pip install -r requirements.txt`.

---



---

> Built as part of hands-on exploration of LangChain agents and tool use with real APIs.
