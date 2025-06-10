# Email-Spam-Detection-ML-Algorithm
## Abstract
The purpose of this project was to select a topic and implement practical machine learning algorithms to find a viable solution. The project included developing a solution to classify emails as spam or non-spam. We worked with a Kaggle dataset of more than 500,000 samples, where there existed a significant imbalance between non-spam (518k) and spam (7k) emails. In order to address this, we implemented undersampling aimed to balance the two datasets. We then selected algorithm types that were suitable for classification type problems. The models we focused on were SGDClassifier, Support Vector Machine (SVM), and Decision Tree. We compared data metrics like recall and F1 score to determine which model would best perform in spam detection. Upon testing and training the models, we compared the results and established that the SVM model was the most appropriate, showing a good balance between accuracy and reliability. This project portrays how the application of machine learning in everyday issues can be addressed when the right model is applied.

## Introduction
Email phishing is on the rise as we adapt to a work-from-home mindset. With one innocent click on a link, attackers can gain access to all of your sensitive information. There are methods to counteract this with spam filters. However, they aren’t entirely reliable at catching all suspicious emails. This shortcoming calls for a smarter and more adaptable approach using machine learning. This report will explore different methods of applying machine learning techniques to classify emails as spam or not spam. A dataset was pulled from Kaggle, prepared by Ethan Cratchley. It comprises 500,000 email samples with different attributes such as the number of spelling errors. The goal of this project is to train and test multiple models using this dataset, analyze the results, and determine which model performs best in detecting spam.


## Attributes
The emails were classified by the owner of the data set, and qualified below based on the presence of different types of words, the length of the emails, numbers of links, spelling mistakes, and urgent keywords,  and the classification of each of the emails. 

## Exploration & Visualization:
The initial class distribution was highly imbalanced; there are approximately 518 thousand emails that are classified as “Not Spam”, compared to the  approximately 7 thousand emails that are labeled as “Spam”. 
Before any of this data was processed, the team created some visualizations to display the distributions of the data. Using the Pandas, and matplotlib libraries in Python, the team was able to successfully create visualizations that tell the story of the data. 


The figure above displays the distribution of all of the emails, based on the number of words. As it can be seen, over 99.9% of emails are under a few thousand words, while there are a few outliers; the most notorious being labeled by the blue arrow in the image, is an email containing roughly 2.25 million words. The existence of these outliers makes it harder to visually see these patterns, as seeing these patterns, as most of the points are compacted to plot the outlier. 
On the same plot, circled in red, the Spam data points are shown.  The colors of the points were mapped, so the red dots point to spam, while the green dots are the Non Spam emails. The data is very disproportionate; there are 517897 Non spam, and 6949 Spam emails in this dataset per the image below, which represents a screenshot of the  “ .info( ) ” function as part of the Pandas Library.  This demonstrates that there is a 75:1 split of the  Not Spam : Spam ratio, and this large ratio, with the amount of outliers, makes it very difficult to see obvious patterns in the data set. 

## Data
The first step to processing the data was to check the rows we have for missing values. Using the Pandas Library data Visualization, there exists an array of features and functions that can be used to manipulate the data, to convert it to usable. As seen above, the data does not appear to have any missing or “N/A” values. This is a good sign, as it means the data has been cleaned and verified previously. 

There was one manipulation that was done to the data to understand it better towards the end of  the run; Converting the label from an integer, by mapping the values of the column, to 0 for Not Spam, and 1 is for Spam email. This was the first manipulation for the data to be able to improve readability.  Every single data type in this data frame is an integer.
Next, the data was partitioned, by the label, and the team down-selected the number of emails from each of the Spam categories, to be at a  1:1 ratio. In other words, the team chose 6949 out of the 517897 Non spam emails, and kept all 6949 Spam emails, to have the largest, but even data set possible. See image below. 

As you can see this is a balanced data frame. Now the team created histograms to visualize the data. Below is an image of a scatter plot of the emails, of the now balanced, down-selected data frame. 

As the data has been manipulated, the red dots are more visible. The plots show a bit more of the distributions, and the placement of the many points is evident. This data does not include any of the aforementioned outliers, and the distribution is a bit more clear, even though there is no evident pattern at this point. 

## Materials and Methods
Of the total 500,000 samples, 7,000 spam emails were going undetected. This highlights the  unreliability of the spam filter, although it is miniscule one spam email is all that is needed to steal information from a company. To address this issue, several supervised machine learning models were developed from labeled data. The dataset was extracted from a kaggle dataset prepared by Ethan Cratchlet, containing over 500,000 email samples. With a large gap between Spam emails and non-spam emails the spam emails dataset was undersampled to balance the dataset. Both datasets were then split 80/20 for training and testing respectively. We selected Support vector machines (SVM), SGD classifier and decision tree as they were best suited for classification problems. After each model was trained and tested from the same dataset, their performance metrics: F1 score, recall, and precision were compared. SVM had a good balance between all categories and therefore was chosen as the most effective in catching spam emails.

## Discussion
Various machine learning models were developed to catch spam emails, which include SGDClassfier, SVM, and Decision Tree. The performance of each model was determined from their F1-scores, precision, and recall. Precision measures how accurate the model was in classifying if an email was spam. For example, high precision dictates the model didn’t incorrectly classify non-spam emails as spam. Recall measures how well the model detects spam. High recall dictates that most spam emails were correctly identified as spam. This can be true even if the model classifies non-spam as spam. F1-score gives the mean of precision and recall, essentially representing the models overall performance. A higher F1 score would indicate a good balance between recall and precision. 

### SGDClassifier
The SGDClassifier had a train/test precision of 56%, a train/test recall of 87% and 88%, and a train/test F1 score of 68% and 69%. The model was able to identify most spam emails but had lots of false positives.

### Support Vector Machine (SVM)
The SVM model had a train/test precision of 73% and 71%, a train/test recall of 73% and 72%, and a train/test F1 score of 73% and 71%. The model showed the most balanced performance across all metrics, demonstrating a reliable and robust spam detection model.

### Decision Tree
The Decision Tree had a train/test precision of 63% and 61%, a train/test recall of 85% and 83%, and a train/test F1 score of 72% and 71%. The model was effective in catching spam emails but similar to SVM produced a lot of false positives. However, the best results were found when the depth was capped at 3, to prevent overfitting. 

## Results
Out of all the models, SVM outperformed the others as it had high recall, precision, and F1 score. The model demonstrated a good balance of each performance metric, making it more consistent than the other models, which performed better in one category but worse in another.


## Conclusion
In conclusion, this project demonstrated the application of machine learning to solve a real-world problem. In this case, classifying spam emails was the goal of the project. The models best suited for this task were found to be SGDClassifier, SVM, and Decision Trees. After pulling a dataset from Kaggle and splitting it for training and testing, each model was evaluated based on its performance outputs. This was done through a decision matrix to determine the most effective model in comparison to their performance metrics. Although the models had their strengths, SVM was the most effective overall. It was the most consistent model in each performance category, yielding a model that correctly classified spam emails at a good rate while minimizing false positives. This project underscores the effectiveness of machine learning in making processes like spam email filters more advanced and secure in a world that is in constant technological advancement.

## References
Cratchley, E. (2025). Email Phishing Dataset. Kaggle. Retrieved May 1, 2025, from https://www.kaggle.com/datasets/ethancratchley/email-phishing-dataset

## Appendix
Google Collab Notebook: https://colab.research.google.com/drive/1Zl5cLb8G0oTg4Cx5gm3RUzghhWOThSN_?usp=sharing 
Kaggle Dataset: 
 https://www.kaggle.com/datasets/ethancratchley/email-phishing-dataset 
