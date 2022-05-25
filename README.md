# Twitter-Sentiment-Analysis

<div>
<img style="float: right;" src="images/sentiment.png" width=250/>
</div>

## Business Problem

This analysis was complete for the Marketing team at Resale Electronics. In preparation for Resale Electronics’ Twitter Ad Campaign the team is in need of a model that can correctly identify their target audience. Their goal is to only have people who have either tweeted positively or neutrally about Apple or Google products included as recipients of their Ad Campaign.

## The Data

The dataset in this analysis comes from CrowdFlower and contained tweets that referenced Google or Apple. This analysis used 9,065 tweets that were ranked by humans as having a positive, negative, or neutral sentiment. The dataset had three columns: tweet text, emotion, and product. The target variable was emotion.

<div>
<img style= src="images/positivecloud.png" width=250/>
</div>

<div>
<img style= src="images/neutralcloud.png" width=250/>
</div>

## Methods

The datasets' `tweet_text` columns were cleaned to help remove distracting noise that can negatively impact the models’ performance. The data was split into a training and test set and the `tweet_text` columns was tokenized. Stopwords and punctuation were removed. WorldNetLemmatizer was used to reduce the individual words down to their simplest form to help the same word not be viewed as different words by the model. 

The datasets were vectorized using CountVectorizer so the data could be modeled. The final model was a Logistic Regression model. Other models were tested such as RandomForest and  MultNB. All models went through hyperparameter tuning using GridsearchCV. 

SMOTE and RandomOverSampler were used to try to help with the fact that the data is imbalanced. However both those methods actually hurt the model’s performance so neither were used in the final model.

## Results

The analysis does create a model that would aid in narrowing down potential targets for Resale Electronics' ad campaign. However, the model has a low accuracy for unseen data. This means that some people who tweet negativity will also be included in the campaign by mistake. As well, there will be some people who tweet positive or neutral and will be incorrectly identify as being negative, therefore falsely removing them from the campaign.

In the end, with each sponsored tweet being so expensive at 50 cents to 2 dollars an ad, it is worth eliminating as many negative tweets as possible. With the knowledge that hardly any people who tweet negatively about Apple or Google go on to purchase their products, an ad to those people could be wasting Resale Electronics budget.

## Conclusion

In summary this analysis showed:
- The final model had an overall accuracy of 69% at correctly identifying the emotion in unseen tweets.
- The model is best at identifying neutral emotion tweets, with a precision of 73% on unseen data. 
- As a result I recommend that more data is collected to improve the model. 

This analysis has gotten you one step closer to correctly identifying and finding your target audience by using machine learning to help rip through all the chaos that is twitter to help you find your potential customers. However, this analysis showed that more information is needed. As a result of the findings, I recommend that you collect more data. Giving more tweets for the model to build off of will improve its performance. Spending the effort to get more data & analyzing the data again can save money in the long run since a well performing model gives you your best shot at finding your correct ad audience. 

Next steps also can include using more complex Deep Natural Language Processing methods such as neural networks.

## For More Information

See the full analysis here: [Jupyter Notebook](./Twitter_Sentiment_Analysis.ipynb) or review the presentation: [presentation](./Twitter_Sentiment_Presentation.pdf).

## Repository Structure

```
├── data
├── images
├── Twitter_Sentiment_Analysis.ipynb
├── Twitter_Sentiment_Presentation.pdf
└── README.md
```