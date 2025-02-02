# Changelog

This changelog contains the notable updates to the **RAG-Driven Generative AI** repository.   
🐬 Indicates *new bonus notebooks* to explore.

## [February 2,2025]

### 🐬OpenAI o3 bonus notebook

Implementing OpenAI o3 to run a RAG task:
`3_Augmented_Generation_o3.ipynb`

The `o3` was made using the standard GPT-4o structure.

Deployed with openai==1.61.0

## [December 5,2024]

### 🐬xAI grok-beta bonus notebook

Implementing grok-beta to introduce RAG techniques:
`Chapter01/RAG_Overview_Grok.ipynb`

## [December 2, 2024]

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
    


