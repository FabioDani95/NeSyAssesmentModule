# Pipeline 5 V1: Document-to-KG

Neurosymbolic AI pipeline for extracting structured knowledge from remanufacturing documentation.

## Architecture

**Flow**: PDF → Parse → Filter → Extract (LLM) → Ground → Validate → Neo4j

**Modules**:
1. Document Processor (PDF parsing)
2. Semantic Retriever (chunk filtering)
3. Neural Extractor (LLM entity extraction)
4. Grounding Engine (link to T-Box)
5. Symbolic Validator (constraint checking)
6. Feedback Manager (STUB - V1.1)
7. Conflict Resolver (STUB - V1.1)
8. Neo4j Populator (A-Box write)

## Setup
```bash
# Create virtual environment
python3 -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Configure environment
cp .env.example .env
# Edit .env with your API keys
```

## Usage
```bash
# Run pipeline
python -m src.main --input data/raw/citiz/manual.pdf

# Run tests
pytest tests/
```

## Project Structure
```
pipeline5/
├── config/          # Configuration files
├── schemas/         # JSON Schema contracts
├── src/
│   ├── modules/     # 8 pipeline modules
│   ├── models/      # Pydantic data models
│   ├── clients/     # External service wrappers
│   └── utils/       # Helper functions
├── tests/
│   ├── contract/    # Contract tests (I/O validation)
│   └── unit/        # Unit tests (utilities)
└── output/          # Generated extractions (gitignored)
```

## Development Status

- ✅ **V1**: Linear pipeline (no feedback loop)
- ⏳ **V1.1**: + Feedback loop + Conflict resolution
- ⏳ **V2**: Advanced monitoring, Docker deployment

## Author

Fabio Daniele - PhD Candidate, SUPSI, Switzerland