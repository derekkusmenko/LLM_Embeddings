LLM Embedding Project

Using LLM embedding vectors as inputs to models to determine whether or not there is an increase in prediction performance due to LLM's contextualizing the data.

Files:

embedding_test.ipynb

embeddings_test.ipynb is a jupyter notebook that extracts LLM embedding vectors to then use as inputs to a NN to predict claim frequency compared to using just the raw features.

The LLM used is the DeepSeek-R1-Distill-Qwen-1.5B model. The embeddings layer is extracted and stored in its own file, then a model is built just using these embeddings to improve computational speed.
The code to do this is taken from https://huggingface.co/spaces/hesamation/primer-llm-embedding?section=embeddings_in_action_%28deepseek-r1-distill-qwen-1.5b%29

The embeddings file is ~900MB and is stored in a onedrive folder as embeddings_qwen.pth: [https://utoronto-my.sharepoint.com/:u:/g/personal/derek_kusmenko_mail_utoronto_ca/ESXTsd3nX_1JtzFGX5hY-ykBvQ1uyMOWlz1LKEjPbsaCmA?e=V9yG4c](https://utoronto-my.sharepoint.com/:f:/r/personal/derek_kusmenko_mail_utoronto_ca/Documents/LLM%20Embedding%20Research?csf=1&web=1&e=Gljs1C)

Note that this code returns the embeddings of each token. I have used mean pooling to create one embedding per prompt.

Data used in this notebook is the French Motor Claims Dataset, taken from https://www.kaggle.com/datasets/floser/french-motor-claims-datasets-fremtpl2freq
