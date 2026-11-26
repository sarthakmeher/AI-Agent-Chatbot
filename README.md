
# 🤖 AI Agent Chatbot


## 📌 Project Overview

AI Agent Chatbot is an AI-powered conversational application that allows users to interact with different Large Language Models (LLMs) through an interactive interface.

The application integrates Groq and OpenAI models using LangChain and LangGraph. Users can select their preferred model provider, customize the system prompt, enter queries, and enable web search through the Tavily search tool.

The project follows a frontend-backend architecture using Streamlit for the user interface and FastAPI for backend API communication.

## ✨ Features

- 🤖 AI-powered conversational chatbot.
- 🔄 Multiple LLM provider support.
- ⚡ Groq model integration.
- 🧠 OpenAI model integration.
- 🔍 Optional web search using Tavily.
- ⚙️ Customizable AI system prompts.
- 🌐 Streamlit-based interactive interface.
- 🚀 FastAPI backend integration.
- 🔗 REST API communication between frontend and backend.
- 🔐 Environment-based API key configuration.

## 🧠 Supported AI Models

| Provider | Models |
|---|---|
| Groq | Llama 3.3 70B Versatile |
| Groq | Mixtral 8x7B |
| OpenAI | GPT-4o Mini |

The available models are configured in the frontend and backend code.

## 🏗️ Project Architecture

```text
              👤 User
                 |
                 ▼
       🌐 Streamlit Frontend
          (frontend.py)
                 |
                 ▼
          🔗 HTTP Request
                 |
                 ▼
          ⚡ FastAPI Backend
           (backend.py)
                 |
                 ▼
          🤖 AI Agent Logic
            (agent.py)
                 |
          ┌──────┴──────┐
          ▼             ▼
      Groq LLM       OpenAI LLM
          |             |
          └──────┬──────┘
                 |
          🔍 Tavily Search
          (Optional Tool)
                 |
                 ▼
          💬 AI Response
                 |
                 ▼
          🌐 Streamlit UI
```

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| 🐍 Python | Core programming language |
| 🦜 LangChain | LLM integration and tools |
| 🧠 LangGraph | AI agent orchestration |
| ⚡ Groq | LLM inference |
| 🤖 OpenAI | LLM integration |
| 🔍 Tavily | Web search functionality |
| 🚀 FastAPI | Backend API |
| 🌐 Streamlit | Frontend interface |
| 📦 Pydantic | Request validation |
| 🔐 Python-dotenv | Environment variable management |
| 🔗 Requests | HTTP communication |

## 📁 Project Structure

```text
AI-Agent-Chatbot/
│
├── 📄 agent.py
├── 📄 backend.py
├── 📄 frontend.py
├── 📄 requirements.txt
├── 🔐 .env
├── 📄 .gitignore
└── 📘 README.md
```

**File descriptions:**

- `agent.py` – Initializes Groq and OpenAI LLMs, configures Tavily search, and creates the AI agent.
- `backend.py` – Defines the FastAPI application and `/chat` endpoint.
- `frontend.py` – Creates the Streamlit interface and sends user queries to the backend.
- `.env` – Stores API credentials locally.
- `requirements.txt` – Lists Python dependencies.

## ⚙️ How It Works

1. The user opens the Streamlit chatbot interface.
2. The user selects an LLM provider: Groq or OpenAI.
3. The user selects an available model.
4. The user defines a custom system prompt.
5. The user optionally enables web search.
6. The query is sent to the FastAPI backend through the `/chat` endpoint.
7. The backend validates the request using Pydantic.
8. The AI agent processes the query using the selected LLM.
9. If enabled, Tavily search provides web search results to the agent.
10. The generated response is returned to the Streamlit frontend.

## 🚀 Installation and Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/sarthakmeher/AI-Agent-Chatbot.git
```

### 2️⃣ Navigate to the Project Directory

```bash
cd AI-Agent-Chatbot
```

### 3️⃣ Create a Virtual Environment

```bash
python -m venv venv
```

Activate on Windows:

```bash
venv\Scripts\activate
```

### 4️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

### 5️⃣ Configure API Keys

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_groq_api_key
OPENAI_API_KEY=your_openai_api_key
TAVILY_API_KEY=your_tavily_api_key
```

Replace the placeholders with your actual API keys.

### 6️⃣ Start the FastAPI Backend

Open the first terminal:

```bash
uvicorn backend:app --host 127.0.0.1 --port 9999 --reload
```

FastAPI server:

```text
http://127.0.0.1:9999
```

Swagger API documentation:

```text
http://127.0.0.1:9999/docs
```

### 7️⃣ Start the Streamlit Frontend

Open a second terminal:

```bash
streamlit run frontend.py
```

The chatbot interface will open in your browser.

## 🔍 API Endpoint

**Endpoint:** `/chat`

**Method:** `POST`

The backend accepts:

```json
{
  "model_name": "llama-3.3-70b-versatile",
  "model_provider": "Groq",
  "system_prompt": "Act as a smart and friendly AI chatbot",
  "messages": ["Explain artificial intelligence"],
  "allow_search": true
}
```

## 🎯 Learning Outcomes

- 🤖 Working with Large Language Models.
- 🧠 Building AI agents using LangGraph.
- 🔗 Integrating multiple LLM providers.
- 🔍 Implementing web search tools.
- ⚡ Developing REST APIs using FastAPI.
- 🌐 Building interactive interfaces using Streamlit.
- 🔐 Managing API keys through environment variables.
- 🏗️ Designing frontend-backend application architecture.

## 🔮 Future Improvements

- 💬 Add conversation history and memory.
- 🧑‍🤝‍🧑 Implement multiple specialized AI agents.
- 📄 Integrate document-based RAG capabilities.
- 📊 Add response streaming.
- 🗂️ Store conversation history in a database.
- 🎨 Improve the chatbot interface.
- 🔧 Add more LLM providers and model options.

## ⚠️ Security Note

Never commit API keys or `.env` files to a public GitHub repository.

Add the following to `.gitignore`:

```gitignore
.env
venv/
__pycache__/
*.pyc
```

## 👨‍💻 Author

**Sarthak Meher**

🔗 GitHub: [github.com/sarthakmeher](https://github.com/sarthakmeher)

---

<p align="center">
  ⭐ If you find this project useful, consider giving it a star!
</p>
