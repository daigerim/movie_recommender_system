# movie_recommender_system
What is the recommendation system?
A recommender system, or a recommendation system, is a subclass of information filtering system that provides suggestions for items that are most pertinent to a particular user (Wikipedia).

Types of recommendation systems:
Collaborative Recommender system - it is based on collecting & analyzing information & predicting what they will like based on the similarity with other users. 
Content-based recommender system - it is based on the description of the item & profile of the user’s preferred choices.
Hybrid recommender system - it is based on a combination of diverse rating & sorting algorithms. 
https://marutitech.medium.com/what-are-the-types-of-recommendation-systems-3487cbafa7c9

Project architecture: 
Dataset  → Preprocessing → Creating a model → Web app → Deployment

1.0 Dataset
Dataset is from Kaggle : https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata
2.0 Preprocessing 
For preprocessing the data libraries such as numpy, pandas, matplotlib were used.
All the missing values in the dataset were established and deleted.
Also the database was checked for having duplicates.
Then only necessary information from columns was selected and str was converted to list though the ast library for easier use and manipulation of the data.
Columns that have been left: movie_id, title, tags
Tags is the merged information of overview, genres, keywords, cast and crew columns.
3.0 Creating a model
1.0 Generating embeddings
What are embeddings?
 Embeddings are vectors that represent real-world objects, like words, images, or videos, in a form that machine learning models can easily process.
The embeddings were done through the CountVectorizer.
CountVectorizer - a text preprocessing technique commonly used in natural language processing (NLP) tasks for converting a collection of text documents into a numerical representation.
from sklearn.feature_extraction.text import CountVectorizer
All the similar movies (first 5) will be selected according to the distances of the vectors. The distance is calculated using cosine similarity. 
from sklearn.metrics.pairwise import cosine_similarity
To avoid the confusion between the different forms of the same word nltk library was used. 
4.0 Web app 
1.0 Creating VENV (virtual environment in VS Code)
The web application part used movedb api to get the necessary information and streamlit library to do the interface
