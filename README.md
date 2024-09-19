# Spam-Ham-Classifier
Getting lost between spam e-mails might be a hassle as it prevents us from checking our important e-mails. Therefore, I tried to implement some machine learning models for dealing with this issue.

# Supervised Models
For this project, 2 supervised models are used. These are Multinomial Naive Bayes and KNN. Both had very good accuracy scores. All relevant scorings are provided below.

## Multinomial Naive Bayes (MNB) Classifier
Accuracy: 98.71%<br/>
Spam Precision: 98.76%<br/>
Ham Precision: 98.67%<br/>
Spam Recall: 98.72%<br/>
Ham Recall: 98.71%<br/>
Spam F1 Score: 98.74%<br/>
Ham F1 Score: 98.69%

When we observe these scorings, we can conclude that this model has worked really well. Precision for spam e-mails are a little bit higher so we can conclude that a predicted spam label is slightly more likely to be correct compared to a predicted ham label. Recall values are almost the same. This means, the model remembers knowledge about each knowledge equally. MNB is a very good algorithm for variables that can be counted. For this dataset, we can seperate each text to their words and count their occurences. Therefore, getting a high accuracy was expected. Though, I also think MNB also memorized some knowledge which could falsely increase accuracy. For example, when a word only appears in spam e-mails, any test e-mails that has that same word is more likely to be classified as spam. For this we can do a more thorough observation and preprocessing to our data. For example, we could remove some words that could appear either way such as "a", "an" and "the". These words don't provide much to the context and therefore they don't usually determine whether an e-mail is spam or not. Though it is important to also see that an e-mail having these words many times consecutively is more likely a spam. So just removing them could also make us lose knowledge. While context can influence an e-mail being spam or not, we cannot observe that in an easy way with similar models. For those observations a neural network is much more suitable which is why removing words wasn't considered in this project. Overall, even though MNB could have some memorization problems, I am confident with its results.

## K-Nearest Neighbors (KNN) Classifier
Accuracy: 90.68%<br/>
Spam Precision: 87.56%<br/>
Ham Precision: 94.57%<br/>
Spam Recall: 95.24%<br/>
Ham Recall: 85.95%<br/>
Spam F1 Score: 91.24%<br/>
Ham F1 Score: 90.05%

For this classifier, number of neighbors was selected as 3. After cross validation, it is observed that neighbor number 1 has the best score. But the increase in accuracy score was so little and negligible that I decided to follow my own assumpted neighbor number since I was more comfortable with that. If it doesn't effect accuracy that much, I value more knowledge. That's the reason for this choice. When we observe these scorings, we can see that this model also worked really well. The precision of ham predictions is considerably higher than the precision of spam predictions. So with this model, we can be more confident when an e-mail is labeled as ham. On the other hand recall of spam e-mails are considerably higher than recall of ham e-mails. This means KNN model remembers spam mails in a better way. When these two observations are combined, we can conclude that most of the spam e-mails will be correctly detected at the cost of losing some of the ham e-mails. Therefore, KNN is a really good model when we extremely want to get rid of spam e-mails. Variance in these scorings could be a result of the lack of strong relationship between each e-mail. Though, memorization doesn't seem to be an issue and we can use KNN if we also want a more realistic model. This needs a more thorough observation. Overall, KNN is also a good model though it has no selling point other than having a chance of being more realistic because each score of MNB was higher.

# Unsupervised Models
For this project, only a single unsupervised machine learning model is used and that is K-Means Clustering algorithm. All relevant scorings are provided below.

## K-Means Clustering Algorithm
Accuracy: 52.91%<br/>
Spam Precision: 51.97%<br/>
Ham Precision: 100%<br/>
Spam Recall: 100%<br/>
Ham Recall: 4.01%<br/>
Spam F1 Score: 68.39%<br/>
Ham F1 Score: 7.71%

This model didn't really work well. It has a very low accuracy score. Although, it managed to accomplish a single thing. That is classifying every spam e-mail correctly. Therefore, we know any e-mail that is predicted as ham is definitlely ham. Although, this is accomplished by losing almost all of the ham e-mails. So this model isn't anywhere near to being useful in any way. There are multiple reasons for this model being extremely bad. Firstly, our data isn't continuous, we have integer values of word appearances. K-Means works better with continous data, so it performed poorly. Secondly, amount of dimensions was both increased from 1 to many and decreased from many to 2 extremely fast. Therefore, there is a high probability of some knowledge loss. Lastly, it is hard to see a trend when we observe only word counts. A single word appearing or not doesn't affect the labeling that much when there are too many words. Overall, K-Means Clustering worked poorly for these reasons.

# Conclusions
Both of the supervised models worked well and can have some use cases. Though, Multinomial Naive Bayes might be more convenient to use most of time since it has better score in all areas compared to KNN. This was actually expected because Multinomial Naive Bayes works well with things that can be counted and we used word appearance counts for our model fitting. K-Means worked poorly so it has no use cases in my opinion. Details are already provided above. Finally, my short comments about models for this dataset are as follows:<br/>
Multinomial Naive Bayes Classifier: Extremely Useful<br/>
K-Nearest Neighbors (KNN) Classifier: Useful<br/>
K-Means Clustering Algorithm: Not Acceptable

# Kaggle Notebook Links
Link to my supervised learning notebook: [https://www.kaggle.com/code/cengizhanterziolu/supervised-spam-ham-classifier](https://www.kaggle.com/code/cengizhanterziolu/supervised-spam-ham-classifier)<br/>
Link to my unsupervised learning notebook: [https://www.kaggle.com/code/cengizhanterziolu/unsupervised-spam-ham-classifier](https://www.kaggle.com/code/cengizhanterziolu/unsupervised-spam-ham-classifier)

Author: Cengizhan Terzioğlu
