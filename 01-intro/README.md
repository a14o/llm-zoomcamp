# Introduction to Retrieval-Augmented Generation (RAG)

## Types of Searches in Information Retrieval

### 1. Lexical Search (Keyword-Based / Sparse Search)

**Definition:**  
Matches documents based on exact keyword or token overlap with the query.

#### How It Works:
- Tokenize documents and queries into words or terms.
- Build an inverted index mapping tokens to documents.
- At query time, retrieve documents containing the same tokens.
- Score matches based on:
  - Keyword overlap
  - Term Frequency-Inverse Document Frequency (TF-IDF)
  - BM25 scoring

#### Tools:
- [Elasticsearch](https://www.elastic.co/)
- [Apache Lucene](https://lucene.apache.org/)
- [Whoosh](https://whoosh.readthedocs.io/)

---

### 2. Semantic Search (Vector-Based / Dense Search)

**Definition:**  
Matches documents and queries based on **meaning** using dense vector representations (embeddings).

#### How It Works:
- Convert documents into dense vector embeddings using models like BERT or Sentence Transformers.
- Embed the query at runtime.
- Perform nearest neighbor search using vector similarity metrics:
  - Cosine similarity
  - Dot product
- Retrieve the most semantically similar documents.

#### Tools:
- [FAISS](https://github.com/facebookresearch/faiss)
- [Pinecone](https://www.pinecone.io/)
- [Weaviate](https://weaviate.io/)
- [Milvus](https://milvus.io/)
- [Qdrant](https://qdrant.tech/)

---

### 3. Hybrid Search (Lexical + Semantic)

**Definition:**  
Combines strengths of lexical (exact match) and semantic (meaning-based) search for more robust retrieval.

#### How It Works:
- Perform both lexical and vector-based search.
- Combine or rerank results using:
  - Heuristics (e.g., weighted sum of scores)
  - Learning-to-rank models

#### Tools:
- [Elasticsearch with KNN Plugin](https://www.elastic.co/blog/text-similarity-search-with-vectors-in-elasticsearch)
- [Weaviate (Hybrid Mode)](https://weaviate.io/developers/weaviate/hybrid-search)
- Custom fusion logic (e.g., score blending, rank fusion)

---

### Summary Table

| Type     | Match Type         | Uses Embeddings | Index Type      | Best For                          |
|----------|--------------------|-----------------|-----------------|----------------------------------|
| Lexical  | Exact words/tokens  | No              | Inverted Index  | Precise keyword-based matching   |
| Semantic | Semantic meaning    | Yes             | Vector Index    | Conceptual / intent-based search |
| Hybrid   | Combined           | Yes             | Mixed           | Balanced relevance & coverage    |

---

