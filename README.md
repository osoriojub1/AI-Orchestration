# AI Orchestration n8n Workflow

A modular and scalable agentic orchestration system built with [n8n](https://n8n.io/). This system leverages multiple specialized AI agents to handle diverse user requests, from general inquiries to complex task execution and document-based research.

## 🚀 Overview

The AI Orchestration system is designed to provide a unified interface for interacting with various AI capabilities. It uses a hierarchical routing mechanism where a central agent classifies user intent and dispatches tasks to the appropriate specialized orchestrator.

## 🏗️ Architecture

The project is structured into several key components:

### 1. User Interaction Layer
- **User Facing Agent**: The primary entry point for users. It manages the chat session, categorizes user intent (QUESTION, TASK_REQUEST, CONVERSATION, etc.), and provides immediate feedback.
- **Interaction Agent**: A sub-agent within the User Facing Agent that follows strict interaction protocols to ensure a smooth user experience.

### 2. Routing Layer
- **Router**: Acts as the central dispatcher. Based on the classified intent, it routes the request to the relevant specialized orchestrator.

### 3. Specialized Orchestrators
- **Task Orchestrator**: Handles complex, multi-step tasks. It can decompose requests into sub-tasks and execute them sequentially or in parallel.
- **RAG Orchestrator**: Implements Retrieval-Augmented Generation. It uses a Document Retriever and a Summarizer to answer questions based on a specific knowledge base.
- **Email Orchestrator**: Automates email-related workflows, including searching for emails, generating drafts, and sending messages.
- **General Question Agent**: A fallback agent designed to handle broader inquiries that don't fall into the specialized categories.

## 📁 Project Structure

```text
AI Orchestration/
├── AI Agents/
│   ├── Email Orchestrator/      # Email automation workflows
│   ├── General Question Agent/ # General inquiry handler
│   ├── RAG Orchestrator/       # Document-based QA system
│   └── Task Orchestrator/      # Complex task management
├── Router.json                 # Central dispatch logic
└── User Facing Agent.json      # Primary user interface agent
```

## 🛠️ Tech Stack

- **Platform**: [n8n](https://n8n.io/)
- **AI Models**: Google Vertex AI (Gemini)
- **Frameworks**: LangChain (via n8n nodes)
- **Capabilities**: Tool Calling, Sub-workflow Execution, RAG, Task Decomposition

## 🚥 Getting Started

1.  **Import Workflows**: Import the `.json` files into your n8n instance.
2.  **Configure Credentials**: Set up your Google Vertex AI credentials in the relevant nodes.
3.  **Deploy**: Activate the workflows and start interacting via the chat trigger in the "User Facing Agent".

---
*Created with ❤️ for AI-driven automation.*
