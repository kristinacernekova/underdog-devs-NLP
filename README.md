# underdog-devs-NLP
The objective of this notebook is to help admins and stakeholders track trends about what brings people to Underdog Devs. We analyze text responses from applicants and mentees. A previous analysis looked at only single word tokens and did not incorporate the context of other words in the response. We perform Natural Language Processing (NLP) by looking at individual words, phrases, and non-consecutive words based on their frequencies in a response. We also explore topic modeling by performing Latent Dirichlet Allocation (LDA).

Topic modeling and LDA:
Topic modeling allows the user to explore the content of the documents and build new connections between topics they might not have been aware of. Latent Dirichlet Allocation (LDA) is a type of topic modeling in which words are represented as topics, and documents are represented as a collection of these word topics. A useful topic model has big non-overlapping circles scattered throughout the chart instead of being clustered in one quadrant. The package also allows the user to observe the most relevant keywords from the selected topic.

The id2word is a special object that keeps track of the mapping from text to numerical index, and the mapping from numerical index back to text.
The corpus is a specially formatted list containing information about each document.

There are a few limitations to LDA:

The number of topics is fixed and must be known ahead of time.
LDA is unable to represent correlations that provide uncorrelated topics across the documents.
LDA is unsupervised.
LDA presumes words are exchangeable and does not account for sentence structure or multiple-word phrases.
LDA performs better for larger texts and is not very suitable for texts with less than 50 words.

In our specific model, we worked with mock data collected by answering the question: “What are the applicants and mentees hoping to gain from the community?” Through our analysis, we found the most inherently useful graphic to be the chart of two-word token frequencies. For now, this will be the only chart we share with administrators once we create an endpoint, but new trends will likely arise with real data. The three-word tokens may then become more useful for informing admins about what the users want to gain from the community.

Topic Modelling
We built the LDA model and visualized results using the pyLDAvis package. Since our coherence score peaked at num_topics = 5, we tried several different numbers of topics (3, 5, 7), but none of them showed useful topic distribution. Mostly, all the topics used the same common words but with slightly different frequencies. This result is not surprising, since there is a clear objective (topic) why the underdog-devs project was created. Moreover, LDA is not the best fit for our collection, since we worked with short texts (only 3 responses out of 335 are longer than 50 words).
