# Essential MCP Servers

A curated collection of **Model Context Protocol (MCP)** servers for development, automation, documentation access, search, and contextual memory.

This repository serves as a **reference configuration and baseline** for MCP-compatible clients (e.g. IDE integrations, agents, internal tooling).

---

## What is MCP

The **Model Context Protocol (MCP)** is a standard for connecting AI clients to external tools and services in a structured, inspectable way.

MCP servers can:
- Run locally and communicate over `stdio`
- Run remotely and communicate over `http`
- Expose tools such as search, code execution, automation, and knowledge retrieval

---

## Repository Scope

This repository focuses on **essential, general-purpose MCP servers**, not experimental or domain-specific ones.

In scope:
- Browser automation
- Documentation and knowledge access
- Web search
- Code execution
- System / desktop interaction
- Cloud and DevOps tooling
- Context and memory augmentation

Out of scope:
- Application-specific agents
- Non-MCP plugins or SDKs
- Prompt-only tools

---

## Included MCP Servers

### Automation & Execution
- **Playwright MCP** – browser automation and E2E testing
- **Python Execute MCP** – remote Python code execution
- **Desktop Commander MCP** – local filesystem and desktop actions

### Knowledge & Documentation
- **Microsoft Learn MCP** – access to Microsoft technical documentation
- **Microsoft Docs MCP** – legacy docs access
- **YouTube Transcript MCP** – fetch video transcripts

### Search & Retrieval
- **Exa MCP** – semantic web search and content retrieval

### Cloud & DevOps
- **Azure DevOps MCP** – work items, repos, and pipelines
- **Kubernetes MCP** – cluster inspection and operations

### Context & Memory
- **Context7 MCP** – external context retrieval
- **Memory MCP** – persistent local memory store

### Networking
- **Fetch MCP** – generic HTTP requests

---

## Example Configuration

```json
{
  "servers": {
    "playwright": {
      "command": "npx",
      "args": ["@playwright/mcp@latest"],
      "type": "stdio"
    },
    "exa": {
      "command": "npx",
      "args": ["-y", "exa-mcp-server"],
      "env": {
        "EXA_API_KEY": "${input:EXA_API_KEY}"
      },
      "autoApprove": ["web_search_exa"],
      "type": "stdio"
    }
  }
}
