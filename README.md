# Vector Similarity Search
LLM's are not effective to make semantic search with just using words.
To increase their searching & meaning capacity embedding a sentence is a common way.
These embeddings can sum up within a database and create a vector database.
In this work, I've prepared a notebook to make effective semantic search through a local vector
Database with using Faiss library.

The foundation of the Faiss library can be found here --> https://arxiv.org/abs/2401.08281

# What is The Main Contribution of The Faiss?

The distance between two vectors (embedded sentence and query) will be the numerical representation
Of similarity between these two sentences based on embedding. So, if euclidean distance calculated between 
Those two vectors, basically it will be a semantic search.

But that direct search can have large amounts of time to operate. Especially when the input dataset is big.
But in the other hand, when input dataset is grown, the unrelated information with the query and vector database
Is also grown. So, we don't need to search through all of the vectors in the vector database. Instead we can cluster
Them and search through based on the centroids.

Following is the representation of the foundation idea of the Faiss library. The searching happens between the 
Centroids, and the limited vectors around them. So, searching cost will be decreased.

![image](https://github.com/rahmansahinler1/vector_similarity_search/assets/102040290/668b029e-faf5-4979-aa87-f7baeb4433ec)

# Tradeoff Between Accuracy and speed

Decrease on the time required for semantic search will come with it's own cost: decreased accuracy.
The tradeoff between them is quite straightforward: If the amount of vectors increases around the centroid,
Searching will be more accurate but time to search will be increased.

# To Get Started

You can install the necessary libraries from the "requirements.txt" file.
You can create your own embeddings with an open source model or with openai model.
All of the necessarry functions inserted, you just need to adapt them accordingly.
