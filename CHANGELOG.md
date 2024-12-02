# Changelog

This changelog contains the notable updates to the **RAG-Driven Generative AI** repository.   
🐬 Indicates *new bonus notebooks* to explore.

## [December 2,2024]

### Code optimization

 `Chapter01/RAG_Overview.ipynb ` : removed `import time` because it is not necessary in this notebook.

### Code fix

`nltk.download('punkt_tab')` added to `Chapter07/Wikipedia_API.ipynb`

## [November 1, 2024]

### New bonus notebook

OpenAI Reasoning Models such as o1-preview can be used for RAG-Driven Generative AI in the ecosystem designed in Chapter 2.

🐬`Chapter02/3_Augmented_Generation_o1_preview.ipynb` 

## [October 25, 2024]

### Fixed
Fixed attribute error in the `class RetrievalComponent`: of the *Modular RAG* section in `Chapter01/RAG_Overview.ipynb` in Chapter 1.

`self.documents` is now initialized in the fit method to hold the records used for searching and enable the `keyword_search` function to access them without error.   

```python
def fit(self, records):
    self.documents = records  # Initialize self.documents here
    if self.method == 'vector' or self.method == 'indexed':
        self.tfidf_matrix = self.vectorizer.fit_transform(records)
```
    


