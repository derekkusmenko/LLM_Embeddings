LLM Embedding Project

Using LLM embedding vectors as inputs to models to determine whether or not there is an increase in prediction performance due to LLM's contextualizing the data.

Files:

gemini_pca_investigation.ipynb

Python notebook using Gemini Embedding model embeddings for prompts constructed from the French Motor Claims Dataset, taken from https://www.kaggle.com/datasets/floser/french-motor-claims-datasets-fremtpl2freq. 

This notebook fits a Poisson GLM on the embeddings generated from the Gemini Embedding model in two ways. 1. PCA to reduce dimensionality to 48 components. 2. Selecting first 48 columns. The notebook also uses the raw data to fit a GLM specified in section 5.2.4 of Statistical Foundations of Actuarial Learning and its Applications by Wüthrich and Merz.

A Neural Network is also fit to the PCA data as well as the raw data.

Various Plots comparing model test mean poisson deviance are produced for comparison.


OUTDATED: 

embedding_test.ipynb -- outdated
embedding_v2.ipynb
embedding_v2_5p.ipynb

embedding_v2.ipynb is a jupyter notebook that extracts LLM embedding vectors to then use as inputs to a Poisson GLM to predict claim frequency. The Mean Poisson Deviance is then compared between this model and a model from section 5.2.4 of Statistical Foundations of Actuarial Learning and its Applications by Wüthrich and Merz.

The LLM used is the DeepSeek-R1-Distill-Qwen-1.5B model. Data used in these notebooks is the French Motor Claims Dataset, taken from https://www.kaggle.com/datasets/floser/french-motor-claims-datasets-fremtpl2freq. The Raw features are turned into a prompt and fed in batches into the LLM to convert the prompt to a vector of its embeddings. Note that this code returns the embeddings of each token. I have used mean pooling to create one embedding per prompt. The 1.5B model has embedding dimension of 1,536. I have done PCA to reduce the number of components to 44 to match the model from the textbook.


