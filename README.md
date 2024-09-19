# Spam-Ham-Classifier
# Supervised Models
For this project 2 supervised models are used. These are Multinomial Naive Bayes and KNN. Both had very good accuracy scores. All relevant scorings are provided below.

## Multinomial Naive Bayes (MNB) Classifier
Accuracy: 98.71%<br/>
Spam Precision: 98.76%<br/>
Ham Precision: 98.67%<br/>
Spam Recall: 98.72%<br/>
Ham Recall: 98.71%<br/>
Spam F1 Score: 98.74%<br/>
Ham F1 Score: 98.69%

When we observe this scorings, we can conclude that this model has worked really well. Precision for spam e-mails are a little bit higher so we can conclude that a predicted spam label is slightly more likely to be correct compared to a predicted ham label. Recall values are almost the same. This means, the model remembers knowledge about each knowledge equally. MNB is a very good algorithm for variables that can be counted. For this dataset, we can seperate each text to their words and count their occurences. Therefore, getting a high accuracy was expected. Though, I also think MNB also memorized some knowledge which could falsely increase accuracy. For example, when a word only appears in spam e-mails, any test e-mails that has that same word is more likely to be classified as spam. For this we can do a more thorough observation and preprocessing to our data. For example, we could remove some words that could appear either way such as "a", "an" and "the". These words don't provide much to the context and therefore they don't usually determine whether an e-mail is spam or not. Though it is important to also see that an e-mail having these words many times consecutively is more likely a spam. So just removing them could also make us lose knowledge. While context can influence an e-mail being spam or not, we cannot observe that in an easy way with similar models. For those observations a neural network is much more suitable which is why removing words wasn't considered in this project. Overall, even though MNB could have some memorization problems, I am confident with its results.

# Links
[Link to my supervised learning notebook](https://www.kaggle.com/code/cengizhanterziolu/supervised-spam-ham-classifier)<br/>
[Link to my unsupervised learning notebook](https://www.kaggle.com/code/cengizhanterziolu/unsupervised-spam-ham-classifier)
