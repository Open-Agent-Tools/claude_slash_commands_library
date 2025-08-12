---
description: Create a new project from templates with full setup
allowed-tools:
  - bash
  - read
  - edit
  - grep
  - glob
  - task
---

Create a new project using the specified template: $ARGUMENTS

**Output Format**: Use clear section headers, timestamps for each step, and progress indicators for setup operations.

**Tool Validation**: First verify that required tools are installed (git, uv, gh) and the target directory is valid.

**Python Project Defaults**: All Python projects use UV for virtual environment management and package installation. Never use pip, pipenv, or conda.

**Template Options**:
- `python-lib` - Python library with pyproject.toml, tests, CI/CD
- `python-cli` - Python CLI application with Click/Typer
- `python-web` - FastAPI web application
- `python-data` - Data science project with Jupyter notebooks
- `python-langchain` - LangChain agent project with LangGraph support
- `python-adk` - Google Agent Development Kit multi-agent system
- `python-crewai` - CrewAI multi-agent orchestration framework
- `python-autogen` - Microsoft AutoGen conversational agents
- `python-swarm` - OpenAI Swarm lightweight agent framework
- `python-phidata` - Phidata AI assistant framework
- `python-llama-index` - LlamaIndex RAG agents with document indexing
- `python-haystack` - Deepset Haystack NLP pipelines
- `python-semantic-kernel` - Microsoft Semantic Kernel plugin architecture
- `python-agency-swarm` - Agency Swarm hierarchical agent framework
- `node-lib` - Node.js library with TypeScript
- `node-web` - React/Next.js web application
- `rust-lib` - Rust library with Cargo.toml
- `go-cli` - Go CLI application
- `custom` - Interactive template selection

**Project Setup Steps**:

1. **Template Selection**: Determine template from argument or prompt interactively
2. **Directory Creation**: Create project directory with proper naming conventions
3. **Template Scaffolding**: 
   - Clone or copy base template files
   - Replace template variables (project name, author, etc.)
   - Setup proper directory structure
4. **Dependency Management**:
   - For Python: Use `uv init` and `uv add` exclusively for all dependencies
   - For Python: Create virtual environment with `uv venv` and activate with `uv run`
   - For other languages: Install language-specific dependencies
   - Configure package manager files
5. **Git Initialization**:
   - Initialize git repository
   - Create initial commit
   - Setup .gitignore for language/framework
   - Configure git hooks if available
6. **CI/CD Setup**:
   - Create GitHub Actions workflows
   - Setup testing and linting pipelines
   - Configure release automation
7. **Development Environment**:
   - Setup IDE configuration files (.vscode, etc.)
   - Create development scripts
   - Configure debugging setup
8. **Documentation**:
   - Generate README with project info
   - Create CONTRIBUTING.md
   - Setup documentation framework
9. **Testing Framework**:
   - Setup test directory structure
   - Create sample tests
   - Configure test runners
10. **Quality Tools**:
    - Configure linting tools
    - Setup formatters
    - Configure type checking
11. **Final Validation**:
    - For Python: Run `uv run python -m pytest` to test setup
    - For Python: Run `uv build` to verify package builds
    - For other languages: Run initial build/compile
    - Execute basic tests
    - Verify all tools work correctly

**Interactive Prompts**:
- Project name (default: directory name)
- Author name and email
- License type (MIT, Apache, etc.)
- Description
- Python version (for Python projects)
- Additional features (database, API, etc.)

**Template Variables**:
- `{{PROJECT_NAME}}` - Project name
- `{{AUTHOR_NAME}}` - Author name
- `{{AUTHOR_EMAIL}}` - Author email
- `{{DESCRIPTION}}` - Project description
- `{{LICENSE}}` - License type
- `{{YEAR}}` - Current year
- `{{PYTHON_VERSION}}` - Python version

**LangChain Template Structure** (`python-langchain`):
```
{{PROJECT_NAME}}/
├── main.py or app.py              # Entry point - initializes agent, handles interactions
├── agents/
│   ├── __init__.py
│   ├── agent_name.py              # Agent definition with AgentExecutor, LLM, tools
│   ├── tools.py                   # Custom tools for external system interactions
│   └── prompts.py                 # Prompt templates separated from agent logic
├── config/
│   ├── __init__.py
│   └── settings.py                # API keys, model names, environment configs
├── data/                          # Optional data sources
│   ├── __init__.py
│   └── data_sources.py            # Vector store, knowledge base connections
├── utils/                         # Optional utilities
│   ├── __init__.py
│   └── helpers.py                 # Utility functions and helper classes
├── langgraph_app/                 # LangGraph orchestration (if using LangGraph)
│   ├── __init__.py
│   ├── graph.py                   # LangGraph state, nodes, edges definition
│   └── nodes.py                   # Individual node functions/classes
├── tests/
├── pyproject.toml
├── .env                           # Environment variables for API keys
├── .gitignore
└── README.md
```

**LangChain Dependencies**:
- `langchain`
- `langchain-community`
- `langgraph` (if multi-agent workflows needed)
- `python-dotenv` (for .env file support)
- Additional providers as needed (e.g., `langchain-openai`, `langchain-anthropic`)

**Google ADK Template Structure** (`python-adk`):
```
{{PROJECT_NAME}}/
├── .env                           # Environment variables (Google Gemini API keys)
├── agents/
│   ├── __init__.py
│   ├── agent_one/
│   │   ├── __init__.py
│   │   ├── agent.py               # Core agent logic, model, name, description
│   │   └── tools.py               # Optional: Custom Python functions for agent
│   └── agent_two/
│       ├── __init__.py
│       ├── agent.py               # Core agent logic, model, name, description
│       └── tools.py               # Optional: Custom Python functions for agent
├── main.py                        # Entry point - orchestrates multi-agent interactions
├── tests/                         # Optional: Unit and integration tests
│   ├── __init__.py
│   └── test_agents.py
├── pyproject.toml
├── .gitignore
└── README.md
```

**Google ADK Dependencies**:
- `google-adk` (Google Agent Development Kit)
- `python-dotenv` (for .env file support)
- Additional Google services as needed (e.g., `google-cloud-aiplatform`)

**CrewAI Template Structure** (`python-crewai`):
```
{{PROJECT_NAME}}/
├── .env                           # Environment variables and API keys
├── agents/
│   ├── __init__.py
│   ├── researcher.py              # Research agent with role, goal, backstory
│   ├── writer.py                  # Writer agent with specialized skills
│   └── reviewer.py                # Review agent for quality control
├── tasks/
│   ├── __init__.py
│   ├── research_tasks.py          # Research task definitions
│   ├── writing_tasks.py           # Writing task definitions
│   └── review_tasks.py            # Review task definitions
├── tools/
│   ├── __init__.py
│   ├── search_tools.py            # Custom search and research tools
│   └── file_tools.py              # File manipulation tools
├── crews/
│   ├── __init__.py
│   └── main_crew.py               # Crew orchestration and workflow
├── main.py                        # Entry point - crew execution
├── config/
│   ├── __init__.py
│   └── agents.yaml                # Agent configurations
├── tests/
├── pyproject.toml
├── .gitignore
└── README.md
```

**CrewAI Dependencies**:
- `crewai`
- `crewai[tools]` (for additional tools)
- `python-dotenv`
- Additional tools as needed (e.g., `duckduckgo-search`, `requests`)

**AutoGen Template Structure** (`python-autogen`):
```
{{PROJECT_NAME}}/
├── .env                           # Environment variables and API keys
├── agents/
│   ├── __init__.py
│   ├── user_proxy.py              # User proxy agent for human interaction
│   ├── assistant.py               # AI assistant agent
│   ├── code_executor.py           # Code execution agent
│   └── group_chat.py              # Group chat manager
├── functions/
│   ├── __init__.py
│   ├── code_functions.py          # Code execution functions
│   └── tool_functions.py          # Custom tool functions
├── workflows/
│   ├── __init__.py
│   ├── conversation_flow.py       # Conversation workflows
│   └── code_review_flow.py        # Code review workflows
├── config/
│   ├── __init__.py
│   ├── llm_config.py              # LLM configurations
│   └── agent_config.py            # Agent configurations
├── main.py                        # Entry point - conversation orchestration
├── tests/
├── pyproject.toml
├── .gitignore
└── README.md
```

**AutoGen Dependencies**:
- `pyautogen`
- `openai` (or other LLM providers)
- `python-dotenv`
- `docker` (optional for code execution)

**Swarm Template Structure** (`python-swarm`):
```
{{PROJECT_NAME}}/
├── .env                           # Environment variables and API keys
├── agents/
│   ├── __init__.py
│   ├── triage_agent.py            # Initial routing agent
│   ├── sales_agent.py             # Sales specialist agent
│   └── support_agent.py           # Support specialist agent
├── functions/
│   ├── __init__.py
│   ├── handoff_functions.py       # Agent handoff functions
│   └── tool_functions.py          # Custom tool functions
├── utils/
│   ├── __init__.py
│   ├── context_manager.py         # Context switching utilities
│   └── response_handler.py        # Response processing
├── main.py                        # Entry point - swarm orchestration
├── config/
│   ├── __init__.py
│   └── swarm_config.py            # Swarm configuration
├── tests/
├── pyproject.toml
├── .gitignore
└── README.md
```

**Swarm Dependencies**:
- `openai-swarm`
- `openai`
- `python-dotenv`

**Phidata Template Structure** (`python-phidata`):
```
{{PROJECT_NAME}}/
├── .env                           # Environment variables and API keys
├── assistants/
│   ├── __init__.py
│   ├── research_assistant.py      # Research assistant with tools
│   ├── data_assistant.py          # Data analysis assistant
│   └── web_assistant.py           # Web search assistant
├── knowledge/
│   ├── __init__.py
│   ├── documents/                 # Document storage
│   ├── vector_db.py               # Vector database setup
│   └── knowledge_base.py          # Knowledge base management
├── tools/
│   ├── __init__.py
│   ├── web_tools.py               # Web search and scraping tools
│   ├── data_tools.py              # Data processing tools
│   └── file_tools.py              # File manipulation tools
├── workflows/
│   ├── __init__.py
│   └── research_workflow.py       # Research workflow orchestration
├── main.py                        # Entry point - assistant interactions
├── config/
│   ├── __init__.py
│   └── phi_config.py              # Phidata configuration
├── tests/
├── pyproject.toml
├── .gitignore
└── README.md
```

**Phidata Dependencies**:
- `phidata`
- `openai` (or other LLM providers)
- `pgvector` (for PostgreSQL vector storage)
- `python-dotenv`

**LlamaIndex Template Structure** (`python-llama-index`):
```
{{PROJECT_NAME}}/
├── .env                           # Environment variables and API keys
├── agents/
│   ├── __init__.py
│   ├── query_agent.py             # Query engine agent
│   ├── chat_agent.py              # Chat engine agent
│   └── rag_agent.py               # RAG agent with custom tools
├── data/
│   ├── documents/                 # Document storage for indexing
│   ├── __init__.py
│   └── loaders.py                 # Document loaders and parsers
├── indices/
│   ├── __init__.py
│   ├── vector_index.py            # Vector store index setup
│   ├── graph_index.py             # Knowledge graph index
│   └── summary_index.py           # Summary index for documents
├── engines/
│   ├── __init__.py
│   ├── query_engine.py            # Custom query engines
│   ├── chat_engine.py             # Custom chat engines
│   └── retrieval_engine.py        # Custom retrieval engines
├── tools/
│   ├── __init__.py
│   ├── document_tools.py          # Document processing tools
│   └── search_tools.py            # Search and retrieval tools
├── main.py                        # Entry point - agent orchestration
├── config/
│   ├── __init__.py
│   └── llama_config.py            # LlamaIndex configuration
├── tests/
├── pyproject.toml
├── .gitignore
└── README.md
```

**LlamaIndex Dependencies**:
- `llama-index`
- `llama-index-embeddings-openai`
- `llama-index-llms-openai`
- `llama-index-vector-stores-chroma` (or other vector stores)
- `python-dotenv`

**Haystack Template Structure** (`python-haystack`):
```
{{PROJECT_NAME}}/
├── .env                           # Environment variables and API keys
├── pipelines/
│   ├── __init__.py
│   ├── indexing_pipeline.py       # Document indexing pipeline
│   ├── rag_pipeline.py            # RAG query pipeline
│   └── search_pipeline.py         # Search and retrieval pipeline
├── components/
│   ├── __init__.py
│   ├── retrievers.py              # Custom retrieval components
│   ├── generators.py              # Custom generation components
│   └── preprocessors.py           # Document preprocessing components
├── data/
│   ├── documents/                 # Document storage
│   ├── __init__.py
│   └── document_store.py          # Document store configuration
├── agents/
│   ├── __init__.py
│   ├── search_agent.py            # Search agent with tools
│   └── qa_agent.py                # Question answering agent
├── tools/
│   ├── __init__.py
│   ├── web_tools.py               # Web scraping and search tools
│   └── file_tools.py              # File processing tools
├── main.py                        # Entry point - pipeline execution
├── config/
│   ├── __init__.py
│   └── haystack_config.py         # Haystack configuration
├── tests/
├── pyproject.toml
├── .gitignore
└── README.md
```

**Haystack Dependencies**:
- `haystack-ai`
- `sentence-transformers`
- `faiss-cpu` (or other vector databases)
- `python-dotenv`

**Semantic Kernel Template Structure** (`python-semantic-kernel`):
```
{{PROJECT_NAME}}/
├── .env                           # Environment variables and API keys
├── plugins/
│   ├── __init__.py
│   ├── core_plugin/
│   │   ├── __init__.py
│   │   ├── text_functions.py      # Text processing functions
│   │   └── math_functions.py      # Mathematical functions
│   └── web_plugin/
│       ├── __init__.py
│       └── search_functions.py    # Web search functions
├── skills/
│   ├── __init__.py
│   ├── conversation_skill.py      # Conversation management
│   └── planning_skill.py          # Planning and orchestration
├── planners/
│   ├── __init__.py
│   ├── sequential_planner.py      # Sequential plan execution
│   └── action_planner.py          # Action-based planning
├── memory/
│   ├── __init__.py
│   ├── semantic_memory.py         # Semantic memory store
│   └── volatile_memory.py         # Temporary memory
├── agents/
│   ├── __init__.py
│   └── sk_agent.py                # Semantic Kernel agent
├── main.py                        # Entry point - kernel orchestration
├── config/
│   ├── __init__.py
│   └── sk_config.py               # Semantic Kernel configuration
├── tests/
├── pyproject.toml
├── .gitignore
└── README.md
```

**Semantic Kernel Dependencies**:
- `semantic-kernel`
- `openai` (or other LLM providers)
- `python-dotenv`
- `aiohttp` (for async operations)

**Agency Swarm Template Structure** (`python-agency-swarm`):
```
{{PROJECT_NAME}}/
├── .env                           # Environment variables and API keys
├── agency/
│   ├── __init__.py
│   ├── ceo/
│   │   ├── __init__.py
│   │   ├── ceo.py                 # CEO agent - main orchestrator
│   │   └── instructions.md        # CEO instructions and goals
│   ├── developer/
│   │   ├── __init__.py
│   │   ├── developer.py           # Developer agent
│   │   ├── instructions.md        # Developer instructions
│   │   └── tools/                 # Developer-specific tools
│   │       ├── __init__.py
│   │       └── code_tools.py
│   └── researcher/
│       ├── __init__.py
│       ├── researcher.py          # Researcher agent
│       ├── instructions.md        # Researcher instructions
│       └── tools/                 # Research-specific tools
│           ├── __init__.py
│           └── search_tools.py
├── shared_tools/
│   ├── __init__.py
│   ├── file_tools.py              # Shared file manipulation tools
│   └── communication_tools.py     # Inter-agent communication
├── workflows/
│   ├── __init__.py
│   └── project_workflow.py        # Project execution workflow
├── main.py                        # Entry point - agency orchestration
├── config/
│   ├── __init__.py
│   └── agency_config.py           # Agency configuration
├── tests/
├── pyproject.toml
├── .gitignore
└── README.md
```

**Agency Swarm Dependencies**:
- `agency-swarm`
- `openai`
- `python-dotenv`
- Additional tools as needed (e.g., `requests`, `beautifulsoup4`)

**Error Handling**: If any step fails, attempt to fix the issue automatically. If unable to fix, report the specific error and provide cleanup instructions.

**Post-Setup Instructions**:
- Display next steps for development
- Show available commands (test, build, etc.)
- Provide quick start guide
- Suggest development workflow

The template type provided is: $ARGUMENTS