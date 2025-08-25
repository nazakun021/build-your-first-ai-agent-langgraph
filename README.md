# Build Your First AI Agent with LangGraph

## Introduction

This workshop will walk you through building your very first AI agent using **LangGraph**, a framework built on top of LangChain for creating agentic applications.  

We’ll cover:  
- Setting up your environment  
- Running Jupyter notebooks for experimentation  
- Using LangGraph Studio and LangSmith to visualize and debug your agents  
- Exploring APIs and integrations like GroqCloud, Google AI Studio and Tavily  

By the end of this workshop, you’ll have a working understanding of LangGraph, as well as a few custom-built agents you can extend further.  

---

## Setup

### Python Version

To get the most out of this course, please ensure you're using **Python 3.11 or later**. 
This version is required for optimal compatibility with LangGraph. If you're on an older version, 
upgrading will ensure everything runs smoothly.
```bash
python3 --version
```

### Clone repo
```bash
git clone https://github.com/nazakun021/build-your-first-ai-agent-langgraph.git
cd build-your-first-ai-agent-langgraph
```

### Create an environment and install dependencies
#### Mac/Linux/WSL
```bash
python3 -m venv langgraph-workshop-env
source langgraph-workshop-env/bin/activate
pip install -r requirements.txt
```
#### Windows PowerShell
```powershell
python3 -m venv langgraph-workshop-env
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process
langgraph-workshop-env\Scripts\Activate.ps1
pip install -r requirements.txt
```

### Running notebooks
```bash
jupyter notebook
```

### Setting up API Keys  
You’ll need an API key to connect to the service. 
Make sure to **store your API keys somewhere safe**—for example, in a password manager or a `.env` file (if you’re using something like the `python-dotenv` library).  

Never hardcode your API keys directly into your code or share them publicly.  

---

### Set GroqCloud API Key
* If you don't have a GroqCloud API key, you can sign up [here](https://console.groq.com/).
*  Set `GROQ_API_KEY` in your `.env` file.

---

### Set Google AI Studio API Key
* If you don't have a Google AI Studio API key, you can sign up [here](https://aistudio.google.com/).
*  Set `GOOGLE_API_KEY` in your `.env` file.

---

### Set LangSmith API Key
* Sign up for LangSmith [here](https://smith.langchain.com/).
* Learn more about LangSmith [here](https://www.langchain.com/langsmith) and check the [docs](https://docs.smith.langchain.com/).  
* Store the following in your `.env` file:  

```env
LANGCHAIN_API_KEY=your-key-here
LANGCHAIN_TRACING_V2=true
```

---

### Set up Tavily API Key (for Web Search)

* Tavily Search API is a search engine optimized for LLMs and RAG, aimed at efficient, 
quick, and persistent search results. 
* You can sign up for an API key [here](https://tavily.com/). 
It's easy to sign up and offers a very generous free tier. Some notebooks later will use Tavily. 
* Set `TAVILY_API_KEY` in your `.env` file.

---

### Example `.env` File
Create a `.env` file in your project root directory and add all your API keys there. Example:  

```env
GROQ_API_KEY=your-groqcloud-key
GOOGLE_API_KEY=your-google-key
LANGCHAIN_API_KEY=your-langsmith-key
LANGCHAIN_TRACING_V2=true
TAVILY_API_KEY=your-tavily-key
```

---

### Set up LangGraph Studio

* LangGraph Studio is a custom IDE for viewing and testing agents.
* Studio can be run locally and opened in your browser on Mac, Windows, and Linux.
* See documentation [here](https://langchain-ai.github.io/langgraph/concepts/langgraph_studio/#local-development-server) on the local Studio development server and [here](https://langchain-ai.github.io/langgraph/how-tos/local-studio/#run-the-development-server). 
* Graphs for LangGraph Studio are in the `x-topic/studio/` folders.
* To start the local development server, run the following command in your terminal in the `/studio` directory:

```
langgraph dev
```

You should see the following output:
```
- 🚀 API: http://127.0.0.1:2024
- 🎨 Studio UI: https://smith.langchain.com/studio/?baseUrl=http://127.0.0.1:2024
- 📚 API Docs: http://127.0.0.1:2024/docs
```

Open your browser and navigate to the Studio UI: `https://smith.langchain.com/studio/?baseUrl=http://127.0.0.1:2024`.

* To use Studio, you will need to create a `.env` file with the relevant API keys
