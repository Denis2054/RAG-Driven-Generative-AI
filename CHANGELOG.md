# Changelog

This changelog contains the notable updates to the **RAG-Driven Generative AI** repository.



## [October 30, 2024]

### Added Vector search explanation**

As explained in the book:    
**vector_search**: Searches through each document and calculates similarity.     
**indexed_search**: Uses a precomputed index (TF-IDF matrix in this case) to compute cosine similarities.

The code of the `class RetrievalComponent` in the Modular RAG section in `Chapter01/RAG_Overview.ipynb` in Chapter 1. has been modified to make the vector search function more educational.

For educational purposes,  `def vector_search(self, query):` now uses a brute-force method. The function vectorizes the query and then compares it to each document. It shows how vector search works at a low level, searching for the best document by going through the list of vectorized documents.

The original function used a `tfidf_matrix` to increase the vector search performance but masks the core concept of vector search: searching through a list of vectors. You can still see this matrix approach in `Chapter01/RAG_Overview_O.ipynb` if you wish to study and use it. 

In any case, the goal of this notebook remains to understand the different methods. In the following chapters, platforms such as Deep Lake, Pinecone, and Chroma seamlessly do the vector and index search work for us, so we don't have to worry about writing code for everything!


### Fixed
Fixed attribute error in the `class RetrievalComponent`: of the *Modular RAG* section in `Chapter01/RAG_Overview.ipynb` in Chapter 1.

`self.documents` is now initialized in the fit method to hold the records used for searching and enable the `keyword_search` function to access them without error.   

```python
def fit(self, records):
    self.documents = records  # Initialize self.documents here
    if self.method == 'vector' or self.method == 'indexed':
        self.tfidf_matrix = self.vectorizer.fit_transform(records)
```
    


