# Azure AI Agents Sample Repository

This repository contains a collection of Jupyter notebooks demonstrating various capabilities of Azure AI Agents using the Azure AI SDK. The notebooks showcase different agent types, tools, and integrations with Azure services.

## Overview

Azure AI Agents are intelligent assistants that can perform tasks, answer questions, and interact with various tools and services. This sample repository demonstrates:

- Basic agent creation and conversation
- Integration with external tools and APIs
- Code interpretation and data analysis
- Search and retrieval capabilities
- Function calling and custom tools
- Agent evaluation and testing

## Prerequisites

- Azure subscription with access to Azure AI services
- Python 3.8 or higher
- Azure CLI (for authentication)
- Azure AI Foundry project setup

## Installation

1. Clone this repository:
```bash
git clone https://github.com/memasanz/mm-agents-sample.git
cd mm-agents-sample
```

2. Install required dependencies:
```bash
pip install -r requirements.txt
```

3. Set up your environment variables (see Environment Variables section below)

4. Login to Azure CLI:
```bash
az login
```

## Notebooks Overview

### 001_QuickStart.ipynb
**Purpose**: Introduction to basic Azure AI Agent creation and simple conversation handling.

**Features**:
- Creates a basic agent without tools
- Demonstrates simple conversation flow
- Shows message handling and response retrieval
- Includes Azure Monitor telemetry integration

**Use Case**: Getting started with Azure AI Agents, understanding basic agent-user interaction patterns.

### 002_BingGrounding.ipynb
**Purpose**: Demonstrates an agent with Bing search grounding capabilities for real-time information retrieval.

**Features**:
- Integrates Bing search as a grounding tool
- Provides real-time web search capabilities
- Shows citation and URL reference handling
- Demonstrates tool call execution tracking

**Use Case**: Building agents that need current information from the web, news updates, or real-time data.

### 003_CodeInterpreter.ipynb
**Purpose**: Shows how to create an agent with code interpretation capabilities for data analysis.

**Features**:
- File upload and processing (CSV data analysis)
- Code execution in a sandboxed environment
- Data visualization and analysis
- Statistical computations on uploaded datasets

**Use Case**: Data analysis, generating insights from datasets, creating visualizations, performing calculations.

### 004_FunctionCalling.ipynb
**Purpose**: Demonstrates custom function calling with weather and datetime functions, including agent evaluation.

**Features**:
- Custom function definitions (weather data, current time)
- Function tool integration
- Agent response evaluation (coherence, intent resolution)
- Multi-turn conversation handling

**Use Case**: Building agents with specific business logic, custom APIs, or specialized functionality.

### 005_agent_tester.ipynb
**Purpose**: Shows integration with external Azure Function Apps for extended capabilities.

**Features**:
- External API integration via Azure Functions
- Weather data retrieval from function apps
- Tool call debugging and monitoring
- Agent evaluation with coherence scoring

**Use Case**: Integrating with existing microservices, external APIs, or Azure Function Apps.

### 007_AISearchAgent.ipynb
**Purpose**: Demonstrates advanced search capabilities using Azure AI Search for document retrieval and Q&A.

**Features**:
- Azure AI Search index creation and management
- Document upload and vectorization
- Semantic search and retrieval
- Knowledge grounding with citations
- Agentic retrieval patterns

**Use Case**: Building knowledge bases, document Q&A systems, enterprise search solutions.

### 008_Agent_tester_001.ipynb
**Purpose**: Additional example of Function App integration with comprehensive evaluation capabilities.

**Features**:
- External function app integration
- Comprehensive agent evaluation (coherence, intent resolution, QA evaluation)
- Tool call monitoring and debugging
- Error handling and response analysis

**Use Case**: Production-ready agents with external service integration and quality assurance.

## Environment Variables

Create a `.env` file in the root directory with the following variables. The table below shows which variables are required for each notebook:

| Environment Variable | Description | 001 | 002 | 003 | 004 | 005 | 007 | 008 |
|---------------------|-------------|-----|-----|-----|-----|-----|-----|-----|
| `PROJECT_ENDPOINT` | Azure AI Foundry project endpoint | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `MODEL_DEPLOYMENT_NAME` | Azure OpenAI model deployment name | ✓ |  | ✓ | ✓ | ✓ |  | ✓ |
| `AZURE_OPENAI_GPT_MODEL` | Azure OpenAI GPT model name |  | ✓ |  |  |  | ✓ |  |
| `AZURE_AI_AGENT_NAME_01` | Agent name for notebook 001 | ✓ |  |  |  |  |  |  |
| `AZURE_AI_AGENT_NAME_02` | Agent name for notebook 002 |  | ✓ |  |  |  |  |  |
| `AZURE_AI_AGENT_NAME_03` | Agent name for notebook 003 |  |  | ✓ |  |  |  |  |
| `AZURE_AI_AGENT_NAME_04` | Agent name for notebook 004 |  |  |  | ✓ |  |  |  |
| `AZURE_AI_AGENT_NAME` | Agent name for notebooks 005, 008 |  |  |  |  | ✓ |  | ✓ |
| `BING_CONNECTION_NAME` | Bing search connection name |  | ✓ |  |  |  |  |  |
| `FUNC_KEY` | Azure Function App key for external calls |  |  |  |  | ✓ |  |  |
| `AZURE_OPENAI_ENDPOINT` | Azure OpenAI service endpoint |  |  |  | ✓ | ✓ | ✓ | ✓ |
| `AZURE_OPENAI_KEY` | Azure OpenAI service API key |  |  |  | ✓ | ✓ |  | ✓ |
| `AZURE_OPENAI_DEPLOYMENT` | Azure OpenAI deployment name for evaluation |  |  |  | ✓ | ✓ |  | ✓ |
| `AZURE_API_VERSION` | Azure OpenAI API version |  |  |  | ✓ | ✓ |  | ✓ |
| `AGENT_MODEL` | Agent model name for AI Search |  |  |  |  |  | ✓ |  |
| `AZURE_SEARCH_ENDPOINT` | Azure AI Search service endpoint |  |  |  |  |  | ✓ |  |
| `AZURE_SEARCH_INDEX` | Azure AI Search index name |  |  |  |  |  | ✓ |  |
| `AZURE_OPENAI_GPT_DEPLOYMENT` | GPT deployment for AI Search |  |  |  |  |  | ✓ |  |
| `AZURE_OPENAI_EMBEDDING_DEPLOYMENT` | Embedding deployment for AI Search |  |  |  |  |  | ✓ |  |
| `AZURE_OPENAI_EMBEDDING_MODEL` | Embedding model for AI Search |  |  |  |  |  | ✓ |  |
| `AZURE_SEARCH_AGENT_NAME` | Agent name for AI Search |  |  |  |  |  | ✓ |  |
| `AZURE_SEARCH_API_KEY` | Azure AI Search API key |  |  |  |  |  | ✓ |  |

### Sample .env file:
```env
# Required for all notebooks
PROJECT_ENDPOINT=https://your-project.eastus2.api.azureml.ms

# Model deployments
MODEL_DEPLOYMENT_NAME=gpt-4-turbo
AZURE_OPENAI_GPT_MODEL=gpt-4

# Agent names (use different names for each)
AZURE_AI_AGENT_NAME_01=quickstart-agent
AZURE_AI_AGENT_NAME_02=bing-grounding-agent
AZURE_AI_AGENT_NAME_03=code-interpreter-agent
AZURE_AI_AGENT_NAME_04=function-calling-agent
AZURE_AI_AGENT_NAME=function-app-agent

# Bing search (for notebook 002)
BING_CONNECTION_NAME=your-bing-connection

# Function App integration (for notebook 005)
FUNC_KEY=your-function-app-key

# Azure OpenAI for evaluation (notebooks 004, 005, 008)
AZURE_OPENAI_ENDPOINT=https://your-openai.openai.azure.com/
AZURE_OPENAI_KEY=your-openai-api-key
AZURE_OPENAI_DEPLOYMENT=gpt-4-turbo
AZURE_API_VERSION=2024-02-15-preview

# Azure AI Search (for notebook 007)
AGENT_MODEL=gpt-4-turbo
AZURE_SEARCH_ENDPOINT=https://your-search-service.search.windows.net
AZURE_SEARCH_INDEX=your-search-index
AZURE_OPENAI_GPT_DEPLOYMENT=gpt-4-turbo
AZURE_OPENAI_EMBEDDING_DEPLOYMENT=text-embedding-3-large
AZURE_OPENAI_EMBEDDING_MODEL=text-embedding-3-large
AZURE_SEARCH_AGENT_NAME=search-agent
AZURE_SEARCH_API_KEY=your-search-api-key
```

## Usage

1. **Start with the QuickStart notebook** (001_QuickStart.ipynb) to understand basic concepts
2. **Choose notebooks based on your use case**:
   - For web search capabilities: 002_BingGrounding.ipynb
   - For data analysis: 003_CodeInterpreter.ipynb
   - For custom functions: 004_FunctionCalling.ipynb
   - For external service integration: 005_agent_tester.ipynb or 008_Agent_tester_001.ipynb
   - For search and retrieval: 007_AISearchAgent.ipynb

3. **Set up required environment variables** for the specific notebook you want to run
4. **Run the notebooks in Jupyter** or your preferred environment
5. **Monitor agent performance** using the built-in evaluation tools where available

## Key Features Demonstrated

- **Agent Creation**: Setting up agents with different capabilities and tools
- **Tool Integration**: Connecting agents to external services and APIs
- **Conversation Management**: Handling multi-turn conversations and context
- **File Processing**: Uploading and analyzing data files
- **Search Integration**: Implementing semantic search and retrieval
- **Function Calling**: Creating custom tools and business logic
- **Evaluation**: Measuring agent performance and response quality
- **Monitoring**: Tracking agent behavior and tool usage

## Data Files

- `data/nifty_500_quarterly_results.csv`: Sample financial data used in the code interpreter notebook
- `eval_dataset.jsonl`: Evaluation dataset for testing agent responses
- `utils/user_functions.py`: Utility functions for custom tool integration

## Troubleshooting

### Common Issues:

1. **Authentication errors**: Ensure you're logged in via Azure CLI (`az login`)
2. **Missing environment variables**: Check that all required variables are set in your `.env` file
3. **Model deployment not found**: Verify your model deployment names match your Azure OpenAI setup
4. **Connection timeouts**: Check your network connectivity and Azure service availability

### Support:

- Review Azure AI documentation: [Azure AI Documentation](https://docs.microsoft.com/en-us/azure/ai-services/)
- Check Azure AI SDK documentation: [Azure AI SDK](https://github.com/Azure/azure-sdk-for-python/tree/main/sdk/ai)
- Visit Azure AI Foundry: [Azure AI Foundry](https://ai.azure.com/)

## Contributing

Feel free to contribute by:
- Adding new notebook examples
- Improving existing code
- Adding more evaluation metrics
- Enhancing documentation

## License

This project is licensed under the MIT License. See LICENSE file for details.