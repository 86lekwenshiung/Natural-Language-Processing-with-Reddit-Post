# Project 3 - Natural-Language-Processing-with-Reddit-Post

___
## Subreddit Classification : Fake News or World News?

`With the overflowing of information in the current world , we often find it hard to discern between what is real and fake , what is true and false and what is the full story and selective story. Often , we will find rouge players using misleading words to mix into sentences to arouse sentiments or misinformed the public so that the desired reactions could be derived from their victims.
As Data Scientist , are will able to experiment various modelling and processing technique , so that we are able to create well performed text processing model to help the enmass to better differentiate between fake news and real news?`

<a name = 'content_page'></a>
## Table of contents
* [General Overview of Common Words](#General-Info)
* [Models and Summary Results](#Model)
* [Models Results](#Summary)
* [Key House Feature Observation from Models](#Observation)
* [Applying Models on Client's Business Case](#Application)
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


<a name = 'Summary'></a>
## What those number tell us and how we used them for our Business Case?
[(back to top)](#content_page)
* 4 of 5 models performed relatively well with respect to the Validation Dataset , generally not overfitting (Except for RF).
* Validation RMSE in the range of 0.093 - 0.104. This means that on average, the predicted value will be 9.74% - 10.9% away from the actual results.
* On Average, the predicted value will be $17810 to $18840 away from the actual results , depending on the model used.
* Putting these numbers in perspective:
    - AMES Median House Value is $205,900.
    - Mean Sale Price from our dataset is $187,000.
    - For the Business Case studies , our client Current House Value is forecasted at $277,000.
* These numbers give us a high confidence in our models to be used for business case studies. In this study, we will use our Rigde Model to advise our client.


<a name = 'Observation'></a>
## Key House Feature Observation from Models
[(back to top)](#content_page)

- Base on our model , there are many features that have strong correlation with respect to the Sale Price. However in the **standpoint of a seller in our business study** , many of these numeric feature are already cast in stone and not wise to varies (Size related features : House Size , Lot Area)

- Instead , we will study into features that could be physically implemented and improved upon such as House QC and cond , Garage QC and cond , Kitchen QC, etc.

<p align = 'center'>
    <img src = 'images/ridge_feature.png' height="50%" width="50%">
</p>

<a name = 'Application'></a>
## Applying Models on Client's Business Case
[(back to top)](#content_page)

1. We establish the baseline score for our client model, in this example , the key features as show:

| Client's Current House Info | Description |
|---|---|
| Neighborhood | NridgHT |
| House Style  | 2 Story |
| Living Area  | 1,904 SF |
| Functional  | Typical |
| Air Con  | Yes |
| Current House Cond | 5 |
| Current House QC | 8 |
| Current Garage Cond | Typical Average |
| Current Garage QC | Typical Average |

2. Using our Model , we are able to demonstrate the qualitative impact of improving a feature score ; in this Business Case , the house and garage condition.
3. Base on our client's renovation budget , we had proposed him to improve his house and garage condition and advised the corresponding impact. That is a predicted 9% and 3% increase in Sale Price respectively by taking action individually on this feature.

| House Cond<br>(Client's Current) | House QC<br>(Client's Current) | Predicted Sale Price <br>(Current) |
|:---:|:---:|:---:|
| 8 | 5 | $277,000 |
| House Cond<br>(Proposed) | House QC<br>(Proposed) | Predicted Sale Price <br>(Proposed) |
| 9 | 6 | $298,000 |

| Garage Cond<br>(Client's Current) | Garage QC<br>(Client's Current) | Predicted Sale Price <br>(Current) |
|:---:|:---:|:---:|
| 8 | 5 | $277,000 |
| Garage Cond<br>(Proposed) | GarageQC<br>(Proposed) | Predicted Sale Price <br>(Proposed) |
| 9 | 6 | $285,000 |

4. So what if our client had more budget? Well we could give him a range of option to consider.
5. Given sufficient discussion time , we could also explore more feature and advise our client accordingly.
<p align = 'center'>    
    <img src = 'images/House_cond.png' height="49%" width="49%"> 
    <img src = 'images/Garage_cond.png' height="49%" width="49%">
</p>

<a name = 'Conclusion'></a>
## Conclusion & Next Step
[(back to top)](#content_page)

* With our model low RMSE error and good performance in predicting the Sale Price from the features (Not overfitting), this model is able to give an accurate qualitative overview to our client the potential in improving their house features before selling off.
* While we are able to predict qualitatively , we should also take into account that to improve a house feature, renovation budget will be required. Whether that outweighs the increase of SalePrice is not covered in this studies.
* Further ROI component , where it take in both renovation cost , as well as expected increase in Sale Price could be further study so that client is able to make a more informed decision before taking physical action.

<a name = 'Credits'></a>
