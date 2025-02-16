# Chroma DB Implementation with Alternative Embedding Models


A practical implementation of Chroma DB (vector database) demonstrating CRUD operations with multiple embedding models

## Features
- ✅ CRUD operations with Chroma DB
- 📊 Example Colab notebook with practical use cases
- 💾 Data persistence and collection management

# Create collection
collection = client.create_collection(name="docs", embedding_function=embedder)

# Add documents
collection.add(
    documents=["AI is transforming industries", "LLMs enable new applications"],
    metadatas=[{"category": "trends"}, {"category": "technology"}],
    ids=["doc1", "doc2"]
)

# Query documents
results = collection.query(
    query_texts=["What's new in tech?"],
    n_results=1
)

# Sentence Transformers (Local)
from sentence_transformers import SentenceTransformer

embedder = SentenceTransformer('all-MiniLM-L6-v2')
