# MCP Server 

`mcplanggraph` is a Python project that integrates [LangGraph](https://python.langgraph.dev/), [LangChain](https://www.langchain.com/), and [MCP](https://github.com/langchain-ai/langchain) (Model Context Protocol) to build powerful language model workflows with Groq LLM backend support.

## Overview

This project provides infrastructure to define and manage complex LLM-based workflows using LangGraph and coordinate model interaction via MCP. It also integrates with `langchain-groq`, enabling use of Groq’s language models within these workflows.

## Project Structure

```plaintext
mcplanggraph/
├── requirements.txt        # Project dependencies
├── uv.lock                 # Lock file managed by the uv package manager (Python ≥3.13)
```

## Dependencies

Listed in `requirements.txt`:
- `langchain-groq`: Groq LLM integration for LangChain
- `langchain-mcp-adapters`: Adapters for connecting LangChain with MCP
- `mcp`: Model Coordination Context for orchestrating model calls
- `langgraph`: Graph-based orchestration engine for language models

These dependencies allow:

- Building composable LLM workflows (LangGraph)
- Managing model routing and execution logic (MCP)
- Using Groq’s LLM backend via LangChain
- Connecting LangChain tools with MCP-based systems

## Getting Started

### Prerequisites

- Python **3.13+** (as defined in `uv.lock`)
- [uv](https://github.com/astral-sh/uv) — a modern Python package manager

### Installation

1. Clone this repo and navigate to the directory:

   ```bash
   git clone <your-repo-url>
   cd mcplanggraph
   ```

2. Create a virtual environment:

   ```bash
   python3.13 -m venv venv
   source venv/bin/activate
   ```

3. Install dependencies with `uv` (recommended):

   ```bash
   uv pip install -r requirements.txt
   ```

   Or, using pip:

   ```bash
   pip install -r requirements.txt
   ```

### Example Use (Coming Soon)

As the source code isn’t included here, example usage and sample graphs are assumed to be developed separately. Expect modules to define and run LangGraph workflows using Groq-backed LLMs.

---

## Key Technologies

| Tool | Purpose |
|------|---------|
| **LangGraph** | Composable, stateful LLM-based workflows |
| **MCP** | Protocol for coordinating model interactions |
| **LangChain** | Framework for building applications with LLMs |
| **Groq** | High-performance LLM backend |
| **uv** | Modern Python dependency manager for reproducibility |

## Notes

- `.DS_Store` and `mcplanggraph.zip` could not be decoded (likely binary/non-text files) — they are not included in this explanation.
- You must use Python 3.13+ because of how `uv.lock` is defined.
- Ensure `uv` is installed via `cargo install uv` or refer to [uv installation instructions](https://github.com/astral-sh/uv).

---

## License

GNU

