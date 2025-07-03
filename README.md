# Azure AI Agent Service Sample Notebooks

This repository contains sample notebooks demonstrating various capabilities of the Azure AI Agent Service using the Azure AI Foundry SDK.

## Prerequisites

1. Install required packages:
   ```bash
   pip install -r requirements.txt
   ```

2. Create a `.env` file with the required environment variables (see individual notebook requirements below)

3. Ensure you have proper Azure authentication configured (Azure CLI login or service principal)

## Notebook Overview

### `001_QuickStart.ipynb`
**Purpose**: Basic introduction to Azure AI Agent Service - creates a simple agent and demonstrates fundamental operations.

**Required Environment Variables**:
- `PROJECT_ENDPOINT` - Your Azure AI Foundry project endpoint
- `MODEL_DEPLOYMENT_NAME` - Name of your deployed model
- `AZURE_AI_AGENT_NAME_01` - Name for your agent

### `002_BingGrounding.ipynb`
**Purpose**: Demonstrates creating an agent with Bing search grounding capabilities for real-time web information retrieval.

**Required Environment Variables**:
- `PROJECT_ENDPOINT` - Your Azure AI Foundry project endpoint
- `AZURE_OPENAI_GPT_MODEL` - GPT model name
- `MODEL_DEPLOYMENT_NAME` - Name of your deployed model
- `BING_CONNECTION_NAME` - Name of your Bing search connection
- `AZURE_AI_AGENT_NAME_02` - Name for your Bing grounding agent

### `003_CodeInterpreter.ipynb`
**Purpose**: Shows how to create an agent with code interpreter capabilities for data analysis and computation tasks.

**Required Environment Variables**:
- `PROJECT_ENDPOINT` - Your Azure AI Foundry project endpoint
- `MODEL_DEPLOYMENT_NAME` - Name of your deployed model
- `AZURE_AI_AGENT_NAME_03` - Name for your code interpreter agent

### `004_FunctionCalling.ipynb`
**Purpose**: Demonstrates function calling capabilities with custom tools and includes coherence evaluation using Azure AI Evaluation.

**Required Environment Variables**:
- `PROJECT_ENDPOINT` - Your Azure AI Foundry project endpoint
- `MODEL_DEPLOYMENT_NAME` - Name of your deployed model
- `AZURE_AI_AGENT_NAME` - Name for your function calling agent
- `AZURE_OPENAI_ENDPOINT` - Azure OpenAI service endpoint
- `AZURE_OPENAI_KEY` - Azure OpenAI API key
- `AZURE_OPENAI_DEPLOYMENT` - Azure OpenAI deployment name
- `AZURE_API_VERSION` - Azure OpenAI API version

### `005_agent_tester.ipynb`
**Purpose**: Advanced agent testing with Azure Functions integration for external tool calling capabilities.

**Required Environment Variables**:
- `PROJECT_ENDPOINT` - Your Azure AI Foundry project endpoint
- `MODEL_DEPLOYMENT_NAME` - Name of your deployed model
- `AZURE_AI_AGENT_NAME` - Name for your agent
- `FUNC_KEY` - Azure Function app key for external tool calls

### `007_AISearchAgent.ipynb`
**Purpose**: Creates an agent integrated with Azure AI Search for advanced document retrieval and knowledge-based questioning.

**Required Environment Variables**:
- `PROJECT_ENDPOINT` - Your Azure AI Foundry project endpoint
- `AZURE_SEARCH_ENDPOINT` - Azure AI Search service endpoint
- `AZURE_OPENAI_ENDPOINT` - Azure OpenAI service endpoint
- `AGENT_MODEL` - Agent model name (defaults to "gpt-4.1-mini")
- `AZURE_SEARCH_INDEX` - Search index name (defaults to "earth_at_night")
- `AZURE_OPENAI_GPT_DEPLOYMENT` - GPT deployment name (defaults to "gpt-4.1-mini")
- `AZURE_OPENAI_GPT_MODEL` - GPT model name (defaults to "gpt-4.1-mini")
- `AZURE_OPENAI_EMBEDDING_DEPLOYMENT` - Embedding deployment name (defaults to "text-embedding-3-large")
- `AZURE_OPENAI_EMBEDDING_MODEL` - Embedding model name (defaults to "text-embedding-3-large")
- `AZURE_SEARCH_AGENT_NAME` - Agent name (defaults to "earth-search-agent")
- `AZURE_SEARCH_API_KEY` - Azure Search API key (optional if using managed identity)

### `008_Agent_tester_001.ipynb`
**Purpose**: Additional agent testing scenarios and evaluation workflows.

**Required Environment Variables**:
- `PROJECT_ENDPOINT` - Your Azure AI Foundry project endpoint
- `MODEL_DEPLOYMENT_NAME` - Name of your deployed model
- `AZURE_AI_AGENT_NAME` - Name for your agent

## Common Environment Variables

Most notebooks require these core variables:
- `PROJECT_ENDPOINT` - Your Azure AI Foundry project endpoint
- `MODEL_DEPLOYMENT_NAME` - Name of your deployed model

## Security Notes

- Never commit your `.env` file to version control
- Clear notebook outputs before committing to avoid exposing secrets
- Use `jupyter nbconvert --clear-output --inplace *.ipynb` to clear all outputs
- Regenerate API keys if accidentally exposed

## Getting Started

1. Start with `001_QuickStart.ipynb` to understand basic agent creation
2. Explore specific capabilities based on your use case:
   - Web search: `002_BingGrounding.ipynb`
   - Data analysis: `003_CodeInterpreter.ipynb`
   - Custom functions: `004_FunctionCalling.ipynb`
   - External integrations: `005_agent_tester.ipynb`
   - Document search: `007_AISearchAgent.ipynb`
