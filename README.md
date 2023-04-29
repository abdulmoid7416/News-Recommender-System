# News-Recommender-System

This is a group project for the course DSC 478, at DePaul University, taught by Professor Roselyn Tchoau. I along with two friends: Mohammed Abdelghani and Shaik Mohammed Sohaib worked on this project.


## Abstract:

In this work, we developed a Content-based News Recommender Systems. We developed multiple models using various approaches like TF-IDF, Word2Vec, and Weighted similarity between multiple attributes in the dataset. We also experimented with different distance/similarity metrics: cosine similarity, Euclidean distance, and Pearson correlation coefficient. In our experiments, we found that Euclidean similarity works best for this application. Word2Vec gave better results than TF-IDF and Bag-of-Words in case of using single attribute i.e., ‘headline’ for recommendation.


## Dataset Information:

The dataset originally consisted of data from around 200k news articles over the years 2012 and 2018. However, because of shortage of memory/computation, we down-sampled it to around 38k news articles from 2017 January onwards until 2018. The dataset has the following attributes:
• Category: The category of the news article.
• Headline: The headline of the news article.
• Authors: The author(s) of the news article.
• Link: The link of the news article.
• Short_description: A short description of the news article.
• Date: The date on which the news article was published.

During pre-processing, we parsed the link attribute to get the website name, and by visualization, we discovered that all the news articles data were from the same website, i.e., ‘Huffingtonpost’. So, we eliminated this attribute. The dataset link is provided below:
https://www.kaggle.com/datasets/yazansalameh/news-category-dataset-v2


## Methodology:

In this work, we developed content based recommender system, that recommends news articles based on a given article’s features. The steps for developing news recommender system are as follows:
1. Data Pre-processing: We checked for null values and duplicates in the data. Short headlines with less than five words were also removed. We downsampled the dataset to include data from January 2017 onwards. The data consisted of around 38k articles.
2. Data Visualization: We analyzed the dataset to gain insights on the distribution of articles category-wise, year-wise using plots.
3. Text Pre-processing: We applied tokenization and lemmatization to ‘headline’ and ‘short description’ attributes using nltk library and stored the processed text as ‘Processed_Data.csv’.


## 4. Approaches:
  
  a. Bag-of-Words:
  Bag of Words (BoW) is a text representation approach that counts the frequency of occurrence of each word in the text and creates a vector of word frequencies for     each document. In this project, the BoW approach was used to analyze the text in news articles and create a vector representation of the news articles based on the     frequency of words.
  
  b. TF-IDF:
  Term Frequency-Inverse Document Frequency (TF-IDF) is a text representation approach that takes into account the frequency of occurrence of each word in a document     and the frequency of the word in the entire corpus. TF-IDF gives more importance to less frequent words in a corpus. It assigns a weight to each term(word) in a       document based on Term frequency(TF) and inverse document frequency(IDF). TF(i,j) = (# times word i appears in document j) / (# words in document j) IDF(i,D) =         log_e(#documents in the corpus D) / (#documents containing word i) weight(i,j) = TF(i,j) x IDF(i,D) So if a word occurs more number of times in a document but less     number of times in all other documents then its TF-IDF value will be high.
  In this project, along with TF-IDF, we also experimented with cosine similarity, Euclidean distance, and Pearson Correlation for recommending articles.
  
  c. Word2Vec:
  Word2Vec is a text representation approach that creates vector representations of words based on their content. Word2Vec considers the words that frequently appear     together in a text and creates a vector representation of the words that captures the semantic relationships. For a given corpus, during training it observes the       patterns and represents each word by a d-dimensional vector.
  In this project, the TF-IDF approach was used along with cosine similarity and Euclidean distance to analyze the text in news articles and create a vector             representation of the news articles and recommend articles.
  
  d. Weighted similarity between multiple attributes:
  In this approach, the similarity scores of multiple attributes such as headlines, authors, and publishers are combined to compute weighted similarity scores between   the articles. One-hot encoding was used along with word2vec in this approach to calculate similarity. The purpose of one-hot encoding is to compare the articles       based on category information.
  
  
