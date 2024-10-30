# Changelog

This changelog contains the notable updates to the **RAG-Driven Generative AI** repository.



## [October 30, 2024]

### Added Vector search explanation**
Modification of the code of the `class RetrievalComponent`: of the *Modular RAG* section in *RAG_Overview.ipynb in Chapter 1.* to make the vector search function more educational

For educational purposes,  `def vector_search(self, query):` functions now uses a **brute-force method**. The function vectorizes the query and then compares it to each query. It shows how vector search works at low level.

The original function used a `tfidf_matrix`to increase the vector search preformance but masks the core concept of vector search: searching through a list of vectors. You can still see this approach in `Chapter01/RAG_Overview_O.ipynb` if you wish to study and use it.

The `def indexed_search(self, query):` function remains unchanged because it captures the concept of searching through indexes.

To make sure everything is clear:

**vector_search**: Searches through each document and calculates similarity.

**indexed_search**: Uses a precomputed index (TF-IDF matrix) to compute cosine similarities.

The goal of this notebook remains to understand the different methods. In the following chapters, platforms such as Deep Lake, Pinecone, and Chroma seamlessly do the vector and index search work for us so we don't have to worry about writing code for everything!

### Fixed
Fixed attribute error in the `class RetrievalComponent`: of the *Modular RAG* section in *RAG_Overview.ipynb in Chapter 1.*

`self.documents` is now initialized in the fit method to hold the records used for searching and enable the `keyword_search` function to access them without error.   

```python
def fit(self, records):
    self.documents = records  # Initialize self.documents here
    if self.method == 'vector' or self.method == 'indexed':
        self.tfidf_matrix = self.vectorizer.fit_transform(records)
```
    


