# 🎮 UdaPlay - AI Game Research Agent

An intelligent AI agent designed to answer questions about video games using a two-tier information retrieval system combining RAG (Retrieval Augmented Generation) with web search capabilities.

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o--mini-green.svg)
![ChromaDB](https://img.shields.io/badge/ChromaDB-Vector%20Database-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

---

## 📋 Project Overview

UdaPlay is an AI Research Agent capable of:
- **Answering questions** about video games (titles, release dates, platforms, genres, publishers)
- **Two-tier information retrieval:**
  - Primary: RAG over a local dataset using ChromaDB
  - Secondary: Web search using Tavily API when internal knowledge is insufficient
- **Robust evaluation system** to assess retrieval quality and determine when to use web search
- **Generating clear, well-structured responses** with source citations

---

## ✨ Features

### Part 1: RAG Pipeline
- ✅ ChromaDB vector database with persistent storage
- ✅ OpenAI embeddings (text-embedding-ada-002)
- ✅ 15 games indexed with full metadata
- ✅ Semantic search functionality

### Part 2: Agent Implementation
- ✅ **Three core tools:**
  - `retrieve_game` - Search the vector database
  - `evaluate_retrieval` - LLM-as-Judge for quality assessment
  - `game_web_search` - Fallback to Tavily web search
- ✅ State machine workflow for agent logic
- ✅ Short-term conversation memory
- ✅ Structured outputs using Pydantic
- ✅ Source citations in all responses

---

## 🚀 Quick Start

### Prerequisites
- Python 3.10+
- OpenAI API key
- Tavily API key

### Installation

1. **Clone the repository:**
```bash
git clone https://github.com/ferasxd1/UdaPlay---An-AI-Research-Agent-for-the-Video-Game-Industry.git
cd UdaPlay---An-AI-Research-Agent-for-the-Video-Game-Industry
```

2. **Install dependencies:**
```bash
pip install -r Code/project/starter/requirements.txt
```

3. **Set up environment variables:**
Create a `.env` file in `Code/project/starter/`:
```env
OPENAI_API_KEY="your-openai-api-key"
CHROMA_OPENAI_API_KEY="your-openai-api-key"
TAVILY_API_KEY="your-tavily-api-key"
```

4. **Run the notebooks:**
```bash
# First, run Part 1 to set up the RAG pipeline
jupyter notebook Code/project/starter/Udaplay_01_solution_project.ipynb

# Then, run Part 2 to test the agent
jupyter notebook Code/project/starter/Udaplay_02_solution_project.ipynb
```

---

## 📁 Project Structure

```
udaplay-ai-agent/
├── Code/
│   └── project/
│       └── starter/
│           ├── Udaplay_01_solution_project.ipynb  # Part 1: RAG Pipeline
│           ├── Udaplay_02_solution_project.ipynb  # Part 2: Agent
│           ├── games/                              # 15 game JSON files
│           ├── lib/                                # Helper libraries
│           ├── requirements.txt                    # Dependencies
│           └── .env.example                        # Environment template
├── UdaPlay_Project_Submission/                     # Submission package
├── ملخص_المشروع.md                                # Arabic summary
├── كيفية_إنشاء_PDF.txt                            # PDF creation guide
└── README.md                                       # This file
```

---

## 🛠️ Technical Stack

| Component | Technology |
|-----------|-----------|
| **Vector Database** | ChromaDB |
| **Embeddings** | OpenAI text-embedding-ada-002 |
| **LLM** | GPT-4o-mini |
| **Web Search** | Tavily API |
| **Structured Output** | Pydantic |
| **Agent Framework** | Custom State Machine |
| **Language** | Python 3.10+ |

---

## 📊 Agent Workflow

```
User Question
     ↓
retrieve_game (ChromaDB)
     ↓
evaluate_retrieval (LLM Judge)
     ↓
Is quality sufficient?
     ├─ Yes → Generate answer with citations
     └─ No → game_web_search (Tavily)
              ↓
         Generate answer with web sources
```

---

## 🧪 Example Queries

```python
# Query 1: Database retrieval
"When was Pokémon Gold and Silver released?"
# → Searches ChromaDB, finds answer, returns with source

# Query 2: Complex query
"Which one was the first 3D platformer Mario game?"
# → Retrieves multiple results, evaluates, provides answer

# Query 3: Web search fallback
"What is Rockstar Games working on right now?"
# → Database insufficient, falls back to web search
```

---

## 📄 Documentation

- **[ملخص_المشروع.md](./ملخص_المشروع.md)** - Comprehensive Arabic summary
- **[كيفية_إنشاء_PDF.txt](./كيفية_إنشاء_PDF.txt)** - Guide to create PDF from notebooks
- **[PROJECT_SUBMISSION_README.md](./UdaPlay_Project_Submission/PROJECT_SUBMISSION_README.md)** - Detailed submission documentation

---

## 📦 Submission Package

The `UdaPlay_Final_Submission.zip` contains:
- Both solution notebooks (.ipynb)
- HTML versions with outputs
- All game data (15 JSON files)
- Helper libraries (13 Python files)
- Requirements and documentation

---

## 🎯 Project Requirements Met

### RAG Pipeline ✅
- [x] Notebook loads and processes JSON files
- [x] Data added to persistent vector database
- [x] Semantic search functionality

### Agent Development ✅
- [x] Three tools implemented (retrieve, evaluate, search)
- [x] Agent workflow (internal → evaluate → web search)
- [x] Stateful agent with conversation management
- [x] State machine implementation
- [x] Clear, structured, cited answers

### Demonstration ✅
- [x] 3+ example queries tested
- [x] Output includes reasoning and tool usage
- [x] Responses include citations

---

## 🔑 API Keys

### OpenAI API Key
Get your key at: https://platform.openai.com/api-keys

### Tavily API Key
Sign up for free (1000 requests): https://app.tavily.com/home

---

## 📝 License

This project is licensed under the MIT License.

---

## 👤 Author

**Feras Khairallah**
- GitHub: [@ferasxd1](https://github.com/ferasxd1)
- LinkedIn: [Feras Khairallah](https://www.linkedin.com/in/feras-khairallah-b51093278)

---

## 🙏 Acknowledgments

- Udacity for the project framework
- OpenAI for GPT-4o-mini and embeddings
- Tavily for web search API
- ChromaDB for vector database

---

## 📧 Contact

For questions or feedback, please open an issue or contact me directly.

---

**⭐ If you find this project useful, please consider giving it a star!**
