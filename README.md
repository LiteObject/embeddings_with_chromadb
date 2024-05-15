# Embeddings with Chromadb
Embeddings have revolutionized the way we represent and process data in machine learning and natural language processing tasks. They allow us to transform high-dimensional, unstructured data into compact, meaningful vector representations. ChromaDB, a powerful vector database, takes embeddings to the next level by providing efficient storage, retrieval, and similarity search capabilities. In this blog post, we'll explore how ChromaDB empowers developers to harness the full potential of embeddings.

## What is embeddings?

## Setup Chroma DB

### Install chromadb package
    pip install chromadb

### Get the chroma client
    import chromadb
    chroma_client = chromadb.Client()

### Create a collection
Collections are where you'll store your embeddings, documents, and any additional metadata. You can create a collection with a name:

    collection = chroma_client.create_collection(name="my_collection")

### Add some text documents to the collection
Chroma will store your text and handle embedding and indexing automatically. You can also customize the embedding model.

```python
    collection.add(
        documents=[
            "This is a document about pineapple",
            "This is a document about oranges"
        ],
        ids=["id1", "id2"]
    )
```

###  Query the collection

```python
results = collection.query(
    query_texts=["This is a query document about hawaii"], # Chroma will embed this for you
    n_results=2 # how many results to return
)
print(results)
```

### Inspect Results


## Links
- [ChromaDB: Getting Started](https://docs.trychroma.com/getting-started)


