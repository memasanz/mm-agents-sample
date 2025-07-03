# Azure AI Agent Service Sample Notebooks

This repository contains a collection of Jupyter notebooks demonstrating various capabilities of the Azure AI Agent Service SDK. Each notebook showcases different agent functionalities, from basic conversational agents to advanced tool-calling and retrieval-augmented generation (RAG) scenarios.

## Notebooks Overview

### `001_QuickStart.ipynb` - Basic Agent Creation
**Purpose**: Demonstrates creating a basic conversational agent using the Azure AI Agent Service SDK. This agent doesn't have tools but can answer questions using its knowledge base.

**What it accomplishes**:
- Creates a simple AI agent without external tools
- Demonstrates basic conversation flow with thread management
- Shows how to handle agent responses and message history
- Illustrates basic agent setup and configuration

**Required Environment Variables**:
- `PROJECT_ENDPOINT` - Azure AI Foundry project endpoint
- `MODEL_DEPLOYMENT_NAME` - Name of the deployed AI model
- `AZURE_AI_AGENT_NAME_01` - Unique name for the agent

### `002_BingGrounding.ipynb` - Web Search Agent
**Purpose**: Creates an agent with Bing Grounding capabilities for web search and real-time information retrieval.

**What it accomplishes**:
- Implements an agent with Bing search integration
- Demonstrates grounded responses with web citations
- Shows how to handle tool calls with external search APIs
- Provides real-time information access through web search

**Required Environment Variables**:
- `PROJECT_ENDPOINT` - Azure AI Foundry project endpoint
- `AZURE_OPENAI_GPT_MODEL` - GPT model name for the agent
- `BING_CONNECTION_NAME` - Name of the Bing search connection
- `MODEL_DEPLOYMENT_NAME` - Name of the deployed AI model
- `AZURE_AI_AGENT_NAME_02` - Unique name for the agent

### `003_CodeInterpreter.ipynb` - Data Analysis Agent
**Purpose**: Demonstrates an agent with code interpreter capabilities for data analysis and file processing.

**What it accomplishes**:
- Creates an agent that can execute Python code
- Processes and analyzes CSV files (uses nifty_500_quarterly_results.csv)
- Performs data analysis and generates insights
- Demonstrates file upload and processing workflows

**Required Environment Variables**:
- `PROJECT_ENDPOINT` - Azure AI Foundry project endpoint
- `MODEL_DEPLOYMENT_NAME` - Name of the deployed AI model
- `AZURE_AI_AGENT_NAME_03` - Unique name for the agent

### `004_FunctionCalling.ipynb` - Custom Function Integration
**Purpose**: Shows how to create an agent with custom function calling capabilities and evaluation metrics.

**What it accomplishes**:
- Implements custom functions (weather fetching, datetime retrieval)
- Demonstrates function tool integration with agents
- Shows automated function execution during conversations
- Includes agent evaluation with coherence and intent resolution metrics

**Required Environment Variables**:
- `AZURE_AI_AGENT_NAME_04` - Unique name for the agent
- `PROJECT_ENDPOINT` - Azure AI Foundry project endpoint
- `MODEL_DEPLOYMENT_NAME` - Name of the deployed AI model
- `AZURE_OPENAI_ENDPOINT` - Azure OpenAI service endpoint
- `AZURE_OPENAI_KEY` - Azure OpenAI API key
- `AZURE_OPENAI_DEPLOYMENT` - Azure OpenAI deployment name
- `AZURE_API_VERSION` - Azure OpenAI API version

### `005_agent_tester.ipynb` - Function Apps Integration
**Purpose**: Demonstrates an agent that leverages Azure Function Apps for external tool calling and includes comprehensive evaluation capabilities.

**What it accomplishes**:
- Integrates with Azure Function Apps for external API calls
- Implements weather information retrieval through Function Apps
- Demonstrates advanced evaluation techniques (coherence, intent resolution, QA evaluation)
- Shows tool call inspection and debugging capabilities

**Required Environment Variables**:
- `PROJECT_ENDPOINT` - Azure AI Foundry project endpoint
- `AZURE_AI_AGENT_NAME` - Unique name for the agent
- `MODEL_DEPLOYMENT_NAME` - Name of the deployed AI model
- `FUNC_KEY` - Azure Function App access key
- `AZURE_OPENAI_ENDPOINT` - Azure OpenAI service endpoint
- `AZURE_OPENAI_KEY` - Azure OpenAI API key
- `AZURE_OPENAI_DEPLOYMENT` - Azure OpenAI deployment name
- `AZURE_API_VERSION` - Azure OpenAI API version

### `007_AISearchAgent.ipynb` - Retrieval-Augmented Generation (RAG)
**Purpose**: Creates an AI agent that uses Azure AI Search for retrieval-augmented generation, enabling question-answering over indexed documents.

**What it accomplishes**:
- Creates and configures Azure AI Search indexes
- Uploads and indexes sample documents (NASA Earth at Night e-book)
- Implements agentic retrieval for document-based question answering
- Demonstrates vector search and semantic search capabilities
- Shows knowledge agent creation and management

**Required Environment Variables**:
- `PROJECT_ENDPOINT` - Azure AI Foundry project endpoint
- `AGENT_MODEL` - Agent model name (defaults to "gpt-4.1-mini")
- `AZURE_SEARCH_ENDPOINT` - Azure AI Search service endpoint
- `AZURE_SEARCH_INDEX` - Search index name (defaults to "earth_at_night")
- `AZURE_OPENAI_ENDPOINT` - Azure OpenAI service endpoint
- `AZURE_OPENAI_GPT_DEPLOYMENT` - GPT deployment name
- `AZURE_OPENAI_GPT_MODEL` - GPT model name
- `AZURE_OPENAI_EMBEDDING_DEPLOYMENT` - Embedding model deployment name
- `AZURE_OPENAI_EMBEDDING_MODEL` - Embedding model name
- `AZURE_SEARCH_AGENT_NAME` - Search agent name (defaults to "earth-search-agent")
- `AZURE_SEARCH_API_KEY` - Azure AI Search API key

### `008_Agent_tester_001.ipynb` - Advanced Function Apps Testing
**Purpose**: An advanced version of agent testing with Function Apps integration, focusing on tool calling and evaluation.

**What it accomplishes**:
- Advanced function app integration for tool calling
- Comprehensive agent testing and evaluation
- Tool call debugging and inspection
- Coherence and intent resolution evaluation

**Required Environment Variables**:
- `PROJECT_ENDPOINT` - Azure AI Foundry project endpoint
- `AZURE_AI_AGENT_NAME` - Unique name for the agent
- `MODEL_DEPLOYMENT_NAME` - Name of the deployed AI model
- Additional evaluation-related variables (same as 005_agent_tester.ipynb)

## Common Environment Variables

Most notebooks require these core variables:
- `PROJECT_ENDPOINT` - Your Azure AI Foundry project endpoint
- `MODEL_DEPLOYMENT_NAME` - The name of your deployed AI model

For evaluation features, you'll also need:
- `AZURE_OPENAI_ENDPOINT` - Azure OpenAI service endpoint
- `AZURE_OPENAI_KEY` - Azure OpenAI API key
- `AZURE_OPENAI_DEPLOYMENT` - Azure OpenAI deployment name
- `AZURE_API_VERSION` - Azure OpenAI API version

## Data Files

The repository includes sample data files and utilities:

### `data/` folder:
- `nifty_500_quarterly_results.csv` - Sample financial data used by `003_CodeInterpreter.ipynb` for data analysis demonstrations

### `utils/` folder:
- `user_functions.py` - Collection of reusable functions for agent tool calling, including:
  - Weather fetching (mock implementation)
  - Date/time utilities
  - Email sending (mock implementation)
  - Mathematical calculations
  - Data processing utilities

### `eval_dataset.jsonl`
- Sample evaluation dataset with query/response/ground_truth pairs for testing agent performance

## Getting Started

1. **Set up Azure Resources**:
   - Create an Azure AI Foundry project and note the endpoint
   - Deploy the required AI models in your project (GPT-4, embedding models)
   - Set up additional services as needed (Bing Search, Azure AI Search, Function Apps)

2. **Configure Environment**:
   - Clone this repository
   - Create a `.env` file in the root directory
   - Add the required environment variables for the notebooks you plan to run

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Notebooks**:
   - Start with `001_QuickStart.ipynb` for basic agent functionality
   - Progress through other notebooks based on your use case
   - Each notebook is self-contained and can be run independently

## Environment Setup Example

Create a `.env` file with the following structure:

```
# Core Azure AI Configuration
PROJECT_ENDPOINT=https://your-project.cognitiveservices.azure.com/
MODEL_DEPLOYMENT_NAME=your-gpt-model-deployment

# Agent Names (customize as needed)
AZURE_AI_AGENT_NAME_01=quickstart-agent
AZURE_AI_AGENT_NAME_02=bing-grounding-agent
AZURE_AI_AGENT_NAME_03=code-interpreter-agent
AZURE_AI_AGENT_NAME_04=function-calling-agent
AZURE_AI_AGENT_NAME=main-agent

# Azure OpenAI (for evaluation features)
AZURE_OPENAI_ENDPOINT=https://your-openai.openai.azure.com/
AZURE_OPENAI_KEY=your-openai-key
AZURE_OPENAI_DEPLOYMENT=your-deployment-name
AZURE_API_VERSION=2024-02-15-preview

# Bing Search (for 002_BingGrounding.ipynb)
BING_CONNECTION_NAME=your-bing-connection

# Azure AI Search (for 007_AISearchAgent.ipynb)
AZURE_SEARCH_ENDPOINT=https://your-search.search.windows.net
AZURE_SEARCH_API_KEY=your-search-key
AZURE_SEARCH_INDEX=your-index-name
AZURE_SEARCH_AGENT_NAME=your-search-agent

# Function Apps (for 005_agent_tester.ipynb and 008_Agent_tester_001.ipynb)
FUNC_KEY=your-function-app-key
```

## Prerequisites

- **Azure AI Foundry project** with appropriate permissions
- **Deployed AI models** (GPT-4, text-embedding models)
- **Python 3.8+** with Jupyter notebook support
- **Additional Azure services** as needed:
  - Bing Search API (for web grounding)
  - Azure AI Search (for RAG scenarios)
  - Azure Function Apps (for external tool integration)
