# Vector DB
Vector databases use embeddings to capture the meaning of data, gauge the similarity between different pairs of vectors, and navigate large datasets to identify the most similar vectors. 
In the context of large language models, the primary use of vector databases is retrieval augmented generation (RAG), where text embeddings are stored and retrieved for specific queries.
However, the versatility of vector databases extends beyond RAG and makes it possible to build a wide range of applications quickly with minimal coding.

### Main applications of Vector Databases

1. **Semantic Search**: Search that goes beyond keyword matching, focussing on meaning of content/context of user query. 
2. **RAG**
3. **Recommender System**
4. **Facial Similarity**
5. **Anomaly Detection**: e.g identify unusual patterns in logs

### What are Embeddings?
- A type of data compression which transforms messy data (text, images, audio video etc) into compact format for ML algorithms
- Most often numeric vectors(aka arrays) with 100s or 1000s of elements
- Preserve information such that "similar" items have proportionally "similar" embedding vectors
- Similarity is measured with vector algorithms (cosine, euclidean, etc)
- What does similarity mean?
  - If it's a **Text Embedding**, Semantic similarity i.e meaning behind sequence of texts
  - If it`s a **Graph Embeddings**, similarity in position or structure in a graph - can have semantic meaning too


### Embedding Models
- Embedding models have evolved from word to sentence embeddings to now cross encoder embedding models.
- Embedding models create embedding vectors that make it possible to build semantic or meaning based retrieval systems.

![RAG Embedding Architecture](../docs/content/imgs/architecture/rag-embedding-arch-pattern.png)

- Word Embeddings vs Contextualized word embeddings:
  - If a word is simply vectorized, then words with different context get the same vector embeddings. This isn't what we want to do semantic search coz context is lost. 
  - **Contextualized word embeddings** to the rescue. In 2017 introduced **Transformer architecture** which led to creation of LLM's today and also solved issue of contextualized word embeddings.
- Bert Embedding Model common tasks
  - **Text classification**
  - **Named Entity Recognition** (Detecting PII data etc)
  - **Question Answering**
- How do we go from contextualized word embeddings to a full sentence embedding model? (for much greater accuracy)
  - Use **dual encoder architecture** for sentence embeddings
  - Its mostly used to train on Q&A pairs
- RAG: Workflow
  ![RAG Workflow](../docs/content/imgs/workflow/rag-query-workflow.png)
- Why not add everything in context window to RAG?
  - Higher computational cost
    - Longer prompts take more computation to run
    - Model now has to scan every token and perform complex scans
  - Context window limit
    - Eventually you will hit hte limit of LLM's context window
    - Small models have only thousand token while larger models have millions of tokens as context window
- 

