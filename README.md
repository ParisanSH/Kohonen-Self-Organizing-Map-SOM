# Kohonen-Self-Organizing-Map-SOM-
In this mini project, I have tried to train and test a SOM network to do cluster analysis of news collection, from the BBC news website corresponding to stories in five topical areas from 2004-2005. The dataset is a collection of 2225 news documents, categorized into 5 classes ‘business’, ‘entertainment’, ‘politics’, ‘sport’, and ‘tech’.


Text Clustering using SOM
Text clustering is an unsupervised process, used to separate a document collection into some clusters on the basis of the similarity relationship between documents in the collection. Suppose 𝐷 = {𝑑1, … , 𝑑𝑁} be a collection of 𝑁 documents to be clustered. The task is to divide 𝐷 into 𝑘 clusters
𝐶1, … , 𝐶𝑘 where 𝐶1 ∪ … ∪ 𝐶𝑘 = 𝐷 and 𝐶𝑖 ∩ 𝐶𝑗 = ∅, for 𝑖 ≠ 𝑗.
SOM text clustering can be done in two main phases. 
The first phase is document preprocessing, which uses Vector Space Model (VSM) to generate a numeric vector for each text document. 
In the next phase, SOM is applied on the document vectors to obtain document clusters.

Phase 1: Document Preprocessing

By means of VSM, each document 𝑑𝑖 can be represented by an 𝑛-dimensional feature vector 𝒗𝑖 =< 𝑣𝑖1, … , 𝑣𝑖𝑛 >, where 𝑣𝑖𝑗 is a representation of term 𝑡𝑗 in document 𝑑𝑖 and 𝑛 is the number of distinct terms in the document collection 𝐷.

An approach for computing 𝑣𝑖𝑗 is the Term Frequency - Inverse Document Frequency (TF-IDF) weighting scheme. This method computes 𝑣𝑖𝑗 for term 𝑡𝑗 in document 𝑑𝑖 as:
𝑣𝑖𝑗 = log(1 + 𝑡𝑓𝑖𝑗) × log(𝑁/𝑑𝑓𝑗)
where 𝑡𝑓𝑖𝑗 is the frequency of term 𝑡𝑗 in document 𝑑𝑖, and 𝑑𝑓𝑗 is the number of documents in 𝐷 containing term 𝑡𝑗.

First, the ‘BBC-text.csv’ file read and for each document:
1. Removing all non-letter characters from the documents.
2. Extracting all words of the document and removing the short words (length ≤ 2).
3. Removing all stop words (e.g., ‘a’, ‘and’, ‘what’, …), given in file ‘stopwords.txt’.
4. Computing the feature vector for each document, using the TF-IDF weighting scheme.

Phase 2: SOM Clustering
a) Winner-takes-all approach
1. Using all documents to build a SOM with one neuron for each class.
2. Depicting the SOM-hits plot.
3. Computing and reporting the confusion matrix.

b) On-center, off-surround approach
1. Using all documents to build a SOM with 3*3 neurons.
2. Depicting the SOM-hits plot.
3. Computing the Euclidean distance of all documents to their winner neurons and summing up the distances.
4. Repeating steps 1-3 for 4*4 and 5*5 topologies.

