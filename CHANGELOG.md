# Changelog

This changelog contains the notable updates to the **RAG-Driven Generative AI** repo.



## [October 25, 2024]

### Fixed
Fixed attribute error in the `class RetrievalComponent`: of the *Modular RAG* section in *RAG_Overview.ipynb in Chapter 1.*

`self.documents` is now initialized in the fit method to hold the records used for searching and enable the `keyword_search` function to access them without error.   

  `def fit(self, records):  
      **self.documents = records**  # Initialize self.documents here   
      if self.method == 'vector' or self.method == 'indexed':   
        self.tfidf_matrix = self.vectorizer.fit_transform(records)`   



## [September 30, 2024]
Defining the structure of the changelog:

### Added
- Adding a new bonus notebook.

### Upgraded
- Upgrading a package in a notebook

### Fixed
- Fixed an issue in a notebook

### Performance Improvements.
- Optimized code 
