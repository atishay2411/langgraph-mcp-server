# MCP Server using LangGraph

`mcplanggraph` is a Python project that integrates [LangGraph](https://python.langgraph.dev/), [LangChain](https://www.langchain.com/), and [MCP](https://en.wikipedia.org/wiki/Model_Context_Protocol) (Model Context Protocol) to build powerful language model workflows with Groq LLM backend support.

## Overview

This project enables coordination between multiple LLM-powered tools using MCP, Groq-backed LangChain agents, and LangGraph orchestration. It includes working tool servers, a LangChain agent client, and integration with Groq.

## What is Model Context Protocol (MCP)?

The **Model Context Protocol (MCP)** is an open standard designed to enable seamless communication between LLM-based applications and external tools, data sources, or services. Introduced in 2024, it is built on top of JSON-RPC 2.0 and enables tools to be discovered, described, and invoked in a standardized way.

Key features of MCP:
- Standardizes tool/plugin interaction across different LLM ecosystems.
- Supports both local (stdio) and remote (streamable HTTP) transport layers.
- Enables dynamic tool discovery and usage at runtime.
- Facilitates chaining and coordination of multiple tools.

This protocol allows an LLM agent to invoke tools like math operations or weather services programmatically without hardcoding logic for each integration.

## Project Structure

```plaintext
mcplanggraph/
├── client.py              # LangChain+Groq agent client using MCP tools
├── mathserver.py          # Math MCP tool server using stdio
├── weather.py             # Weather MCP tool server using HTTP
├── main.py                # Simple entrypoint script
├── requirements.txt       # Basic dependencies (alt to pyproject.toml)
├── pyproject.toml         # Project metadata and dependencies
├── .gitignore             # Git ignore rules
├── .python-version        # Python version pin (3.13)
└── README.md              # Project documentation
```

## Dependencies

Defined in `pyproject.toml` and `requirements.txt`:

- `langchain-groq`: LangChain integration with Groq LLMs
- `langchain-mcp-adapters`: Bridges LangChain tools with MCP servers
- `langgraph`: Graph-based workflow orchestrator
- `mcp`: Model Context Protocol for tool invocation

## Getting Started

### Prerequisites

- Python **3.13+**
- [uv](https://github.com/astral-sh/uv) (optional for lockfile support)
- [Groq API key](https://console.groq.com/) in your `.env` file

### Installation

```bash
# Clone the repo
$ git clone https://github.com/atishay2411/langgraph-mcp-server
$ cd mcplanggraph

# Create a virtual environment
$ python3.13 -m venv .venv
$ source .venv/bin/activate

# Install dependencies
$ pip install -r requirements.txt
# Or use pyproject.toml
$ pip install .
```

Add a `.env` file with:

```env
GROQ_API_KEY=your_api_key_here
```

### Running the Example

Start the weather tool server (HTTP):
```bash
python weather.py
```

Run the client (spawns math tool subprocess):
```bash
python client.py
```

You should see the math and weather responses printed by the agent.

---

## Key Technologies

| Tool | Purpose |
|------|---------|
| **LangGraph** | Stateful LLM workflows |
| **MCP** | Protocol for tool orchestration |
| **LangChain** | Framework for LLM apps |
| **Groq** | High-speed inference backend |
| **uv** | Fast dependency management |

---

## License

GNU

## Contributing

Feel free to open issues or submit pull requests. Contributions are welcome!
