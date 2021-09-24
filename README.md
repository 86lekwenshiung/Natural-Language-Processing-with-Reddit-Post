# Project 3 - Natural-Language-Processing-with-Reddit-Post

___
## Subreddit Classification : Fake News or World News?

With the overflowing of information in the current world , we often find it hard to discern between what is real and fake , what is true and false and what is the full story and selective story. Often , we will find rouge players using misleading words to mix into sentences to arouse sentiments or misinformed the public so that the desired reactions could be derived from their victims. 

In this notebook , I had extracted datas from 2 subreddits post : [r/fakwnews](https://www.reddit.com/r/fakenews/) and [r/World News](https://www.reddit.com/r/worldnews/). At the point of data extraction (Sep 2021) , with the controversy of many 'exciting' news and tweets from the previous POTUS (2016 - 2000) during election periods, as well as the recent US withdrawal from Afghanistan and the ongoing Covid19 Pandemic , there is no doubt there will be numerous posts that transient these 2 posts. The objective of this project is to experiment various modelling and processing technique , so that we are able to create well performed text processing model to better differentiate between fake news and real news.

<a name = 'content_page'></a>
## Table of contents
* [General Overview of Common Words](#General-Info)
* [Models and Summary Results](#Model)
* [Insights from Word Embedding Visualisation](#Observation)
* [Conclusion & Next Step](#Conclusion)

<a name = 'General-Info'></a>
## General Overview of Common Words
[(back to top)](#content_page)

<img src = 'images\common_words.png'>

<a name = 'Model'></a> 
## Models and Summary Results
[(back to top)](#content_page)

|Technique|Models|Description|Accuracy|Precision|Recall|F1 Score|
|---|---|---|---|---|---|---|
|Tokenisation| Random Forest Classifier|Text vectorization|0.764865|0.737828|0.920561|0.819127|
|Word Embedding|Bi Direction LSTM|Create Own Embedding|0.778378|0.820388|0.789720|0.804762|
|Word Embedding|Universal Sentence Encoder|Transfer Learning|0.824324|0.809129|0.911215|0.85714|

<a name = 'Observation'></a> 
## Insights from Word Embedding Visualisation
[(back to top)](#content_page)

In this notebook , I had experiment limiting the maximum vocab to 120 and 6,000 respectively. As we could see from our word embedding , due to the limited amount of dataset at 2,000 dataset , the number of vocabs we had limited is set at `120` so as not to dilute the explained variance of the features. (Explained variance reduced to 22% as we increase the vocab limit to 6,000) If we do have more dataset , we could explore more relevant vocabs and have a better representation of the current challenges on various social media outlet, such as twitter , facebook or any popular forum , as a well as better cross studies on how effective are the fake words or fake posts arousing sentiments , moods and actions.

<p align = 'center'>
    <img src = 'images\fakenews_120vocab.PNG' height="100%" width="100%">
    <caption> Fig 2 : Word Embedding with 120 Words (Explained Variance ~ 49%) </caption>
    <img src = 'images\fakenews_6000vocab.PNG' height="100%" width="100%">
    <caption> Fig 3 : Word Embedding with 6,000 Words (Explained Variance ~ 22%) </caption>
</p>

<a name = 'Conclusion'></a>
## Conclusion & Next Step
[(back to top)](#content_page)

**Insights**

Our models performed relatively well in differentiating between post from fake news and world news. The 3 models performed consistently with accuracy between 78% - 83% and F1 score of 83% - 86% , with the transfer learning USE outperforming amongst all.
The differences or the part where the models are confused is probably due to common word associated to both side of the posts such as US , death , which is possibly linked to the Afghan withdrawal , as well as the US handling of Covid 19 . 

**Next Steps in improving model score**
* Try replacing the TensorFlow Hub Universal Sentence Encoder pretrained embedding for the TensorFlow Hub BERT.
* Experimenting with the pretrained GloVe embeddings.
* Getting more dataset
* Getting more quality dataset. For example , can we trained our model on actual world and fakes news first before using it to predict on these social media posts.

**Next Steps in model application**
Although the objective of this project was to attempt to explore techniques and model to classify posts from reddit, this could be further extended to more social mediam outlet such as twitter , facebook or relevant forums to assist in flushing out malicious fake and misformed news. This could also be further extended to other application as well such as detecting potential depression and suicidal posts.
