# Document_Similarity
**Code to process text from html files and calculate similarity scores between the processed texts**

  This code scrapes text from the wikipedia Basketball article and nine additional wikipedia articles with hyperlinks found on the Basketball page.  It processes the text using several NLP libraries including BeautifulSoup and nltk to create a list of unigrams derived from each article, i.e. a 'bag of words' from each article.
  
  The code then converts each unigram into a 50 element long word vector using the Global Vectors for Word Representation glove.6B.50d.txt dictionary (https://nlp.stanford.edu/data/glove.6B.zip) as reference.  The element-wise average of the vectors contained in each article is calculated, then subjected to a Euclidean distance calculation to determine which articles are most similar.
