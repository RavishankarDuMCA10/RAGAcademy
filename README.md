# RAGAcademy

A hands-on, notebook-driven curriculum for building **Retrieval-Augmented Generation (RAG)** systems from the ground up. Each module covers a distinct stage of the RAG pipeline — from raw data ingestion through vector embeddings to fully functional vector-store-backed retrieval.

---

## Project Structure

```
RAGAcademy/
├── 1_DataIngestParsing/          # Module 1 – Data Ingestion & Parsing
├── 2_VectorEmbeddingAndVectorDatabases/  # Module 2 – Embeddings
├── 3_VectorStoresAndVectorDatabases/     # Module 3 – Vector Stores & RAG
├── main.py
├── pyproject.toml
└── requirements.txt
```

---

## Modules

### Module 1 — Data Ingestion & Parsing

> **Directory:** `1_DataIngestParsing/`

Learn how to load and structure data from every common source into LangChain `Document` objects, ready for downstream RAG processing.

| Notebook | Topic |
|---|---|
| `1-dataingestion.ipynb` | Module overview — `Document` structure, text splitters (`RecursiveCharacterTextSplitter`, `CharacterTextSplitter`, `TokenTextSplitter`) |
| `2-dataparsingpdf.ipynb` | PDF parsing with `PyPDFLoader` and `PyMuPDFLoader`; handling encoding artifacts and scanned pages |
| `3-dataparsingdoc.ipynb` | Word document loading with `Docx2txtLoader` and `UnstructuredWordDocumentLoader` (element-level parsing) |
| `4-csvexcelparsing.ipynb` | Tabular data ingestion with `CSVLoader`, `UnstructuredCSVLoader`, and custom pandas pipelines |
| `5-jsonparsing.ipynb` | Nested JSON and JSON Lines parsing with `JSONLoader` and `jq_schema` |
| `6-databaseparsing.ipynb` | SQL database ingestion from SQLite using `SQLDatabase` and `SQLDatabaseLoader` |

---

### Module 2 — Vector Embeddings

> **Directory:** `2_VectorEmbeddingAndVectorDatabases/`

Build intuition for vector representations and plug in real embedding models.

| Notebook | Topic |
|---|---|
| `embedding.ipynb` | Conceptual intro to embeddings; cosine similarity from scratch; `HuggingFaceEmbeddings` with `all-MiniLM-L6-v2` (no API key required) |
| `openaiembeddings.ipynb` | OpenAI embedding API (`text-embedding-3-small`, `text-embedding-3-large`, `text-embedding-ada-002`) — dimensions, cost, and tradeoffs |

---

### Module 3 — Vector Stores & RAG

> **Directory:** `3_VectorStoresAndVectorDatabases/`

Assemble a complete, end-to-end RAG pipeline.

| Notebook | Topic |
|---|---|
| `1-chromadb.ipynb` | Full RAG pipeline: document loading → text splitting → OpenAI embeddings → ChromaDB vector store → similarity search → context-augmented answer generation |

---

## Tech Stack

| Category | Libraries |
|---|---|
| **LangChain** | `langchain`, `langchain-community`, `langchain-openai`, `langchain-groq`, `langchain-huggingface`, `langchain-text-splitters` |
| **Vector Stores** | `chromadb`, `faiss-cpu` |
| **Embeddings** | `sentence-transformers`, `tiktoken` |
| **Document Parsers** | `pypdf`, `pymupdf`, `python-docx`, `docx2txt`, `unstructured`, `pdfminer` |
| **Data / Utilities** | `pandas`, `openpyxl`, `jq`, `matplotlib`, `python-dotenv` |

---

## Getting Started

### Prerequisites

- Python ≥ 3.12
- [`uv`](https://docs.astral.sh/uv/) (recommended) or `pip`

### Install dependencies

```bash
# Using uv (recommended)
uv sync

# Or using pip
pip install -r requirements.txt
```

### Environment variables

Create a `.env` file in the project root:

```env
OPENAI_API_KEY=your_openai_key_here
GROQ_API_KEY=your_groq_key_here     # optional
```

### Run notebooks

```bash
# Activate the virtual environment (if using uv)
source .venv/bin/activate

# Launch Jupyter
jupyter notebook
```

Open any notebook under the module directories and run cells in order.

---

## Learning Path

```
Module 1 → Ingest data from any source into LangChain Documents
Module 2 → Convert documents into vector embeddings
Module 3 → Store embeddings in a vector database and build a RAG system
```
