# Enterprise RAG Assistant for Knowledge Retrieval

An enterprise-grade Retrieval-Augmented Generation (RAG) application designed to provide intelligent access to organizational knowledge. The platform enables users to retrieve, summarize, and contextualize information from enterprise knowledge bases, support articles, technical documentation, and resolution notes using natural language queries. Built with hybrid retrieval, advanced reranking, and citation enforcement, the solution delivers accurate, context-aware, and source-backed responses for enterprise knowledge discovery.

## 🚀 Key Features

* **Enterprise Knowledge Retrieval**: Enables intelligent search across internal knowledge bases, support articles, technical documentation, and resolution notes using natural language.
* **Hybrid Retrieval**: Combines BM25 keyword search with vector-based semantic search to maximize retrieval accuracy and recall.
* **Cross-Encoder Reranking**: Improves response relevance by prioritizing the most contextually appropriate documents before answer generation.
* **Citation Enforcement**: Every generated response is backed by source documents, ensuring transparency, traceability, and trust.
* **Production-Ready Architecture**: Built with FastAPI, Dependency Injection, and a modular architecture for scalability and maintainability.
* **Evaluation Pipeline**: Includes automated quality evaluation to continuously validate retrieval accuracy and response quality before deployment.

## 🛠️ Tech Stack

* **Framework**: FastAPI (Python 3.11)
* **RAG Engine**: LlamaIndex
* **Vector Database**: Qdrant (Local/Remote)
* **LLM Providers**: Ollama, OpenAI, Azure, Gemini, SageMaker
* **User Interface**: Gradio

## 🚦 Getting Started

### Installation

```bash
# Install dependencies with production extras
poetry install --extras "ui llms-ollama embeddings-ollama vector-stores-qdrant"
```

### Running the Application

To launch the Enterprise RAG Assistant using the default production configuration:

```bash
# Set profiles and start
$env:PGPT_PROFILES="ollama"
poetry run python -m production_rag
```

## ⚙️ Configuration

Configuration is managed through YAML profiles located in the project root:

* `settings.yaml` – Global application configuration.
* `settings-ollama.yaml` – Configuration for Ollama-based local LLM execution.
* `settings-local.yaml` – Configuration for local LlamaCPP/HuggingFace execution.

The configuration supports flexible customization of LLM providers, vector databases, retrieval settings, and runtime parameters for different deployment environments.

## 🧪 Evaluation

Run the evaluation pipeline to validate retrieval relevance, citation accuracy, and overall response quality before deployment.

```bash
python production_rag/rag/evaluation/evaluator.py --threshold 0.7
```

## 🛡️ License

This project is licensed under the Apache-2.0 License.
