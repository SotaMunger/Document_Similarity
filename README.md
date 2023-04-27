# Document_Similarity
**Code to process text from html files and calculate similarity scores between the processed texts**

  The code in this notebook comprises a document similarity calculator that quantifies the semantic distance between ten articles found on Wikipedia. The articles were selected by starting at the Wikipedia page for 'Basketball' and randomly clicking on nine hyperlinks found on that page. Hyperlinks to each of the articles follow:
  
https://en.wikipedia.org/wiki/Basketball
https://en.wikipedia.org/wiki/Backboard_(basketball)
https://en.wikipedia.org/wiki/Layup
https://en.wikipedia.org/wiki/James_Naismith
https://en.wikipedia.org/wiki/McGill_University
https://en.wikipedia.org/wiki/Larry_Bird
https://en.wikipedia.org/wiki/1936_Summer_Olympics
https://en.wikipedia.org/wiki/Babe_Didrikson
https://en.wikipedia.org/wiki/Jersey_(clothing)
https://en.wikipedia.org/wiki/Cardiovascular

Text from all articles were extracted on October 25, 2022 and reflect the content on those pages on that date.
  
  The code first extracts and parses text from the ten articles using functions found in the Python libraries urllib and BeautifulSoup4.  It then proceeds to clean and tokenize the texts using the natural language processing libraries Natural Language Toolkit (NLTK) and Regular Expressions (Re) to create ten lists of unigrams.  
  
  The next step was to convert each unigram into a 50 dimensional GloVe vector embeddings using the Global Vectors for Word Representation glove. (glove.6B.50d.txt from https://nlp.stanford.edu/data/glove.6B.zip).  Finally, the element-wise average of the vectors contained in each article were taken, and the pair-wise euclidean distances between every article were calculated.  The results of the calculations follow (with a distance of 0 indicating perfect similarity and greater distances indicating proportionally less similarity):
  
![image](https://user-images.githubusercontent.com/91567553/235012483-168b2ba0-9214-4b02-b0ea-012ae214d775.png)

  The algorithm used to calculate document similarity for this project ignores word order, i.e. if two articles contain the same tokens but have them arranged in different orders, the similarity score between the articles would still be a perfect 0. 
