# Azure AI Agents Sample Repository

This repository contains a collection of Jupyter notebooks demonstrating various Azure AI Agent capabilities using the Azure AI Projects SDK. Each notebook showcases different features and tools that can be integrated with Azure AI agents.

## Prerequisites

Before running these notebooks, ensure you have:

1. **Azure Account**: An active Azure subscription
2. **Azure AI Studio**: Access to Azure AI Studio with a project created
3. **Python Environment**: Python 3.8+ with the required packages
4. **Environment Configuration**: Properly configured `.env` file with required variables

## Setup

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd mm-agents-sample
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure environment variables**:
   Create a `.env` file in the root directory with the required variables (see table below).

## Notebooks Overview

### 001_QuickStart.ipynb
**Purpose**: Introduction to basic agent creation and interaction  
**Description**: Creates a simple agent without tools. Demonstrates basic agent setup, conversation handling, and message retrieval. This is a foundational example showing how to interact with an agent for simple tasks like getting jokes.

**Key Features**:
- Basic agent creation using Azure AI Projects
- Simple conversation handling
- Message history retrieval
- Logging and telemetry setup

### 002_BingGrounding.ipynb
**Purpose**: Web-grounded agent with Bing search capabilities  
**Description**: Creates an agent with Bing grounding tool that can search the web for current information. Demonstrates how to integrate web search capabilities into your agent for real-time information retrieval.

**Key Features**:
- Bing grounding tool integration
- Web search capabilities
- Citation and URL reference handling
- Real-time information retrieval

### 003_CodeInterpreter.ipynb
**Purpose**: Code execution and data analysis capabilities  
**Description**: Demonstrates an agent with code interpreter functionality that can analyze data files, perform calculations, and generate insights. Uses the included CSV file with quarterly financial results.

**Key Features**:
- Code interpreter tool
- CSV data analysis
- Mathematical calculations
- Data visualization capabilities

### 004_FunctionCalling.ipynb
**Purpose**: Custom function calling and tool integration  
**Description**: Shows how to create custom functions that agents can call, including date/time functions and weather simulation. Includes evaluation capabilities for testing agent responses.

**Key Features**:
- Custom function definitions
- Function calling mechanisms
- Response evaluation
- Tool integration patterns

### 005_agent_tester.ipynb
**Purpose**: Agent testing with Azure Function Apps integration  
**Description**: Comprehensive agent testing framework that integrates with Azure Function Apps for tool calling. Includes multiple evaluation metrics like coherence, intent resolution, and QA evaluation.

**Key Features**:
- Azure Function Apps integration
- Weather tool calling via HTTP
- Coherence evaluation
- Intent resolution testing
- QA evaluation metrics

### 007_AISearchAgent.ipynb
**Purpose**: AI Search integration with vector search  
**Description**: Creates an agent that can search through indexed documents using Azure AI Search. Demonstrates vector search, semantic search, and document retrieval capabilities using NASA's "Earth at Night" dataset.

**Key Features**:
- Azure AI Search integration
- Vector search and indexing
- Semantic search configuration
- Document upload and indexing
- Search-based agent responses

### 008_Agent_tester_001.ipynb
**Purpose**: Extended agent evaluation and testing  
**Description**: Similar to 005 but with additional evaluation capabilities. Provides comprehensive testing framework for agent responses including coherence, intent resolution, and answer quality evaluation.

**Key Features**:
- Comprehensive agent evaluation
- Multiple evaluation metrics
- Response quality assessment
- Intent resolution testing

## Environment Variables Configuration

Create a `.env` file in the root directory with the following variables:

| Variable | Required For | Description |
|----------|-------------|-------------|
| `PROJECT_ENDPOINT` | All notebooks | Azure AI Studio project endpoint URL |
| `MODEL_DEPLOYMENT_NAME` | 001, 002, 003, 004, 005, 008 | Name of the deployed model in Azure AI Studio |
| `AZURE_OPENAI_GPT_MODEL` | 002, 007 | Azure OpenAI GPT model name |
| `AZURE_AI_AGENT_NAME_01` | 001 | Unique name for the QuickStart agent |
| `AZURE_AI_AGENT_NAME_02` | 002 | Unique name for the Bing Grounding agent |
| `AZURE_AI_AGENT_NAME_03` | 003 | Unique name for the Code Interpreter agent |
| `AZURE_AI_AGENT_NAME_04` | 004 | Unique name for the Function Calling agent |
| `AZURE_AI_AGENT_NAME` | 005, 008 | Unique name for the agent tester agents |
| `BING_CONNECTION_NAME` | 002 | Bing Search connection name in Azure AI Studio |
| `FUNC_KEY` | 005 | Azure Function App access key |
| `AZURE_OPENAI_ENDPOINT` | 004, 005, 007, 008 | Azure OpenAI service endpoint |
| `AZURE_OPENAI_KEY` | 004, 005, 008 | Azure OpenAI service API key |
| `AZURE_OPENAI_DEPLOYMENT` | 004, 005, 008 | Azure OpenAI deployment name for evaluation |
| `AZURE_API_VERSION` | 004, 005, 008 | Azure OpenAI API version |
| `AZURE_SEARCH_ENDPOINT` | 007 | Azure AI Search service endpoint |
| `AZURE_SEARCH_INDEX` | 007 | Azure AI Search index name (default: earth_at_night) |
| `AZURE_SEARCH_API_KEY` | 007 | Azure AI Search service API key (optional if using managed identity) |
| `AZURE_SEARCH_AGENT_NAME` | 007 | Unique name for the AI Search agent |
| `AGENT_MODEL` | 007 | Agent model name (default: gpt-4.1-mini) |
| `AZURE_OPENAI_GPT_DEPLOYMENT` | 007 | Azure OpenAI GPT deployment for search |
| `AZURE_OPENAI_EMBEDDING_DEPLOYMENT` | 007 | Azure OpenAI embedding deployment |
| `AZURE_OPENAI_EMBEDDING_MODEL` | 007 | Azure OpenAI embedding model name |

### Sample .env file:
```env
# Core Azure AI Studio Configuration
PROJECT_ENDPOINT=https://your-project.cognitiveservices.azure.com/
MODEL_DEPLOYMENT_NAME=gpt-4

# Agent Names (must be unique)
AZURE_AI_AGENT_NAME_01=quickstart-agent
AZURE_AI_AGENT_NAME_02=bing-agent
AZURE_AI_AGENT_NAME_03=code-interpreter-agent
AZURE_AI_AGENT_NAME_04=function-calling-agent
AZURE_AI_AGENT_NAME=agent-tester

# Azure OpenAI Configuration
AZURE_OPENAI_ENDPOINT=https://your-openai.openai.azure.com/
AZURE_OPENAI_KEY=your-openai-key
AZURE_OPENAI_DEPLOYMENT=gpt-4
AZURE_OPENAI_GPT_MODEL=gpt-4
AZURE_API_VERSION=2024-02-01

# Bing Search Configuration
BING_CONNECTION_NAME=your-bing-connection

# Azure Function Apps Configuration
FUNC_KEY=your-function-key

# Azure AI Search Configuration
AZURE_SEARCH_ENDPOINT=https://your-search-service.search.windows.net
AZURE_SEARCH_INDEX=earth_at_night
AZURE_SEARCH_API_KEY=your-search-key
AZURE_SEARCH_AGENT_NAME=earth-search-agent
AGENT_MODEL=gpt-4
AZURE_OPENAI_GPT_DEPLOYMENT=gpt-4
AZURE_OPENAI_EMBEDDING_DEPLOYMENT=text-embedding-3-large
AZURE_OPENAI_EMBEDDING_MODEL=text-embedding-3-large
```

## Data Files

- **`data/nifty_500_quarterly_results.csv`**: Sample financial data containing quarterly results for Nifty 500 companies. Used in the Code Interpreter notebook for data analysis demonstrations.

## Usage

1. Ensure all required environment variables are set in your `.env` file
2. Start Jupyter Lab or Jupyter Notebook:
   ```bash
   jupyter lab
   ```
3. Open any notebook and run the cells sequentially
4. Each notebook is self-contained and can be run independently

## Dependencies

Key dependencies include:
- `azure-ai-projects`: Core Azure AI Studio integration
- `azure-identity`: Azure authentication
- `azure-ai-inference`: AI model inference
- `azure-search-documents`: Azure AI Search integration
- `azure-ai-evaluation`: Agent evaluation capabilities
- `python-dotenv`: Environment variable management
- `openai`: OpenAI API integration

## Notes

- Ensure your Azure AI Studio project has the necessary model deployments
- Some notebooks require specific Azure services (Bing Search, Azure Functions, Azure AI Search)
- Agent names must be unique within your Azure AI Studio project
- The `agent_tester_001.ipynb` file is currently empty and not functional

## Troubleshooting

- **Authentication Issues**: Ensure you're logged into Azure CLI or have proper service principal credentials
- **Missing Environment Variables**: Check that all required variables for your notebook are set in the `.env` file
- **Model Deployment**: Verify that your model deployments are active in Azure AI Studio
- **Resource Access**: Ensure your Azure identity has proper permissions for all required services

For more information on Azure AI Agents, visit the [Azure AI Studio documentation](https://docs.microsoft.com/azure/ai-studio/).