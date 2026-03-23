# AI-Legal Assistant

An intelligent legal assistant system designed to help users understand and navigate Nepali legal cases through semantic search, AI-driven chatbots, and legal strategy recommendations.

## 🎯 Project Overview

AI Legal Assistant combines advanced AI technologies with a comprehensive legal knowledge base to provide:
- **Intelligent Case Search**: Semantic search across Nepali court cases
- **Legal Chatbot**: Interactive AI assistant for legal inquiries
- **Case Analysis**: Detailed case information with contextual insights
- **Strategy Generation**: AI-powered legal strategy recommendations
- **Legal Glossary**: Comprehensive definitions of legal terms and concepts

## 🏗️ Architecture

### Backend (`/backend`)
- **Framework**: FastAPI with Python
- **AI Components**:
  - LLM Integration (Generative AI)
  - Retrieval-Augmented Generation (RAG) Pipeline
  - Agentic Reasoning System (LangGraph)
  - Semantic Search with Qdrant vector database
  - Intelligent Router for query classification
  - Legal Strategy Generator

- **Key Modules**:
  - `agent/`: Core AI agent logic and tools
  - `llm_client.py`: Language model client
  - `rag_pipeline.py`: Document retrieval and augmentation
  - `agent_graph.py`: Multi-agent workflow orchestration
  - `qdrant_kb.py`: Vector database management
  - `intelligent_router.py`: Query routing and classification
  - `response_synthesizer.py`: Response generation and formatting
  - `strategy_generator.py`: Legal strategy recommendations

### Frontend (`/frontend`)
- **Framework**: React 18 with Vite
- **Features**:
  - Case search interface
  - Chat-based legal inquiry
  - Case detail view with metadata
  - Strategy recommendation display
  - Responsive design

- **Key Pages**:
  - `SearchPage.jsx`: Case search interface
  - `ChatPage.jsx`: Interactive chatbot
  - `CaseDetail.jsx`: Individual case details
  - `StrategyPage.jsx`: Legal strategies

### Knowledge Base (`/global_knowledge_base`, `/glossary`)
- Legal case metadata and summaries
- Court information and case type classifications
- Comprehensive legal glossary and terminology
- Legal verdict patterns and outcomes

### Vector Storage (`/qdrant_storage`)
- Semantic embeddings of legal cases
- Vector-based similarity search

### Search Index (`/search_index`)
- FAISS-based full-text search index
- Case corpus and metadata

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- Node.js 16+
- pip or conda

### Backend Setup

1. **Install dependencies**:
```bash
cd backend
pip install -r requirements.txt
```

2. **Configure environment**:
```bash
# Create .env file with required API keys and settings
# Required variables:
# - LLM_API_KEY (for Generative AI)
# - Other configuration parameters
```

3. **Start the server**:
```bash
python main.py
# API will be available at http://localhost:8000
# Docs at http://localhost:8000/docs
```

### Frontend Setup

1. **Install dependencies**:
```bash
cd frontend
npm install
```

2. **Development server**:
```bash
npm run dev
# Client will be available at http://localhost:5173
```

3. **Build for production**:
```bash
npm run build
```

## 📊 Data Processing Pipeline

The system includes a comprehensive data processing pipeline in `/scripts`:
- Data exploration and analysis
- Legal glossary construction
- Case preprocessing and normalization
- Semantic index building
- Qdrant knowledge base initialization
- System metrics and performance monitoring

Key scripts:
- `build_index.py`: Constructs search indices
- `06_build_semantic_index.py`: Creates vector embeddings
- `09_build_qdrant_knowledge.py`: Initializes semantic database

## 🔍 Query Types

The system intelligently handles multiple query categories:

1. **Law Explanation**: Understanding specific laws and legal concepts
2. **Case Recommendation**: Finding similar cases and precedents
3. **Legal Advice**: Guidance for specific legal situations
4. **Loophole Analysis**: Identifying patterns and gaps in legal provisions
5. **General Inquiry**: General questions about the legal system

## 🛠️ API Endpoints

### Main Endpoints
- `GET /`: Health check
- `POST /search`: Semantic case search
- `POST /chat`: Interactive legal chatbot
- `POST /strategy`: Legal strategy generation
- `GET /case/{case_id}`: Case details
- `GET /docs`: Interactive API documentation (Swagger UI)

## 📈 Metrics & Monitoring

The system includes comprehensive monitoring:
- Response quality metrics
- Query classification accuracy
- System health monitoring
- Performance analytics
- Metrics exported to CSV for analysis

View metrics in `/scripts/csv_exports/`

## 💡 Key Technologies

- **LLM**: Google Generative AI
- **Vector Database**: Qdrant
- **Search**: FAISS (Facebook AI Similarity Search)
- **NLP**: Sentence Transformers, HuggingFace Transformers
- **Web Framework**: FastAPI, React
- **Orchestration**: LangGraph
- **Build Tool**: Vite

## 📝 Project Structure

```
├── backend/               # FastAPI backend
│   ├── agent/            # AI agent modules
│   ├── main.py           # Server entry point
│   └── requirements.txt   # Python dependencies
├── frontend/             # React application
│   ├── src/             # React components
│   ├── package.json     # Node dependencies
│   └── vite.config.js   # Vite configuration
├── global_knowledge_base/ # Legal knowledge resources
├── glossary/             # Legal terminology and concepts
├── qdrant_storage/       # Vector database
├── search_index/         # Full-text search index
└── scripts/              # Data processing pipeline
```

## 🔐 Security & Privacy

- API keys and sensitive data are managed through environment variables
- No personal user data is stored in the public knowledge base
- All case data is sourced from public legal records



**Note**: This system is designed for informational purposes. Users should consult qualified legal professionals for actual legal advice.
