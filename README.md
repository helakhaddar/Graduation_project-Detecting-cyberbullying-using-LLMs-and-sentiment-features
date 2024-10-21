# Detecting cyberbullying using LLMs and sentiment features
- Data Preparation:
We prepared our dataset, where we merged three datasets, from different social media platforms: Twitter, Kaggle comments and wikipedia talk pages. Then we extracted the sentiment features, using an already fine-tuned RoBERTa model on our dataset.
- Data preprocessing and analysis:
We performed first data cleaning where we removed punctuation marks, links, urls, emojis,.. then we did the natural language processing (NLP) steps by removing the stopwords, lemmatization, and tokennization
- Modeling:
We choose to work with distilbert, due to the computational ressources that we didn't have. We fine-tuned the Distilbert model by adding the sentiment feature extracted, and adding a fully connected layer over the final hidden state that corresponds to the [CLS] input token. We trained our model on 70% of our dataset, the 15% is left for the validation set to optimize our model, we used the focal loss, the early s²topping technique and adam optimizer. It achieved a really good perfoamnce whith an accuracy of 89.46% on the test set.   
- Evaluation:
For this step we chose to evaluate our model in a complete different dataset where the data here is from twitter and facebook and is the inverse of ours in the distribution where the non cyberbullying class is the majority class. The performance on this different dataset dropped.  

