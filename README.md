# Subeddit Post Classifier

## Introduction

Welcome to my GitHub repository for my Subreddit Post Classifier project. The goal of this project is to build a model to process and analyze a massive [dataset](https://github.com/linanqiu/reddit-dataset) containing over 260,000 posts and comments from various subreddits, which can then use this data to make predictions about where a given post or comment is from. These were all submissions by users to Reddit.com scraped directly from the website by the creator of the linked GitHub repository in 2016. By applying machine learning techniques, specifically a Random Forest Classifier, we are able to predict the subreddit category for given text posts with high accuracy. 

## Purpose

The purpose of this project is twofold: firstly, to demonstrate the power of Natural Language Processing (NLP) and machine learning in classifying text data, and secondly, to provide a practical tool that can automatically categorize Reddit posts. This has numerous applications, from content filtering and recommendation systems to social media monitoring and data analysis.In the age of information overload, the ability to automatically sort and classify vast amounts of text data is invaluable. Not only does it aid in managing the data, but it also enables the extraction of insights and trends from specific communities. This project showcases how a relatively simple machine learning model can provide a high degree of accuracy in text classification tasks, paving the way for more complex and nuanced data analysis.

## Real-World Applications

This classifier can be employed in various real-world scenarios such as:

- **Content Moderation:** Automatically flagging or categorizing posts for review to maintain community standards.
- **Marketing Insights:** Analyzing customer sentiment and interests across different subreddit communities for targeted marketing.
- **Trend Analysis:** Monitoring the popularity and discussion topics within communities over time to identify trends.
- **Custom Feeds:** Creating personalized content feeds for users based on their interests.

## Data
Once again here is the direct link (https://github.com/linanqiu/reddit-dataset) to the github repository from which this data was sourced from, it belongs to Linan Qiu and is under an MIT License. The source contains 51 seperate csv dataset, one for each subreddit. This combined for over 260,000 posts and comments throughout the entire dataset. The CSVs are described as having the following columns:
- `text`: Text of the comment / thread
- `id`: Unique reddit id for the comment / thread
- `subreddit`: Subreddit that the comment / thread belongs to
- `meta`: Metareddit that the comment / thread belongs to. Subreddits belong to metareddits. A subreddit can be `leagueoflegends`. The metareddit for that subreddit would be `gaming`, which can also include the subreddit `dota2`
- `time`: UNIX timestamp of the comment / thread
- `author`: Username of the author of the comment / thread
- `ups`: Number of upvotes the comment / thread received
- `downs`: Number of downvotes the comment / thread received
- `authorlinkkarma`: The author's link karma. [What is Link Karma?](https://www.reddit.com/r/NoStupidQuestions/comments/2idfhk/what_is_link_karma/)
- `authorkarma`: The author's karma. [Reddit FAQ](https://www.reddit.com/wiki/faq) explaining karma.
- `authorisgold`: Boolean indicator for the gold status of the user. `1` for gold users, `0` for non-gold (normal) users. [Reddit FAQ](https://www.reddit.com/wiki/faq) explaining gold status.

## Data Cleaning
1. Since all the datasets were their own csv I started out by combining them all into one.
2. Next I started cleaning the text getting rid of special characters and numbers
3. Then I utilized a corpus of stop words to remove insignificant and common words from the data
4. After that I stemmed the remaining words and got rid of any single letter tokens. 
5. Lastly, I replaced any empty strings with NaN and then dropped those rows.

## Exploratory Data Analysis

In the exploratory data analysis section, we observe a notable reduction in the number of rows. This decrease is primarily due to the removal of less significant words and short tokens, which significantly streamlined the dataset.

The histogram reveals that the most prevalent subreddits in our dataset include categories such as gaming, lifestyle, humor, news, and television. These subreddits play a pivotal role in shaping the classifier, indicating their relative importance in the analysis. Additionally, the analysis sheds light on the most frequent tokens present in the dataset. Interestingly, these tokens are not standard English words. This might be an outcome of the data processing techniques used, or it could indicate the presence of common word roots from non-English languages, considering our filtering was focused on removing only common English terms.

## Models

In this section I test out four differnet models to see which is the best. I have to used 10% of the dataset because using the whole dataset would take too long looping thorough the model then the following grid search. The selected models for this examination were Naive Bayes, SVM (Support Vector Machine), Logistic Regression, and Random Forest. These models were chosen for their robustness and efficacy in handling datasets with a high dimensionality of features, which is a common scenario in complex classification tasks. Each of these models brings unique strengths to the table:

Naive Bayes: Known for its simplicity and speed, especially in text classification and scenarios where the assumption of feature independence holds.

SVM: Highly effective in high-dimensional spaces and versatile due to its kernel trick, making it suitable for non-linear classification.

Logistic Regression: A go-to algorithm for binary classification problems, providing a probabilistic framework and interpretability.

Random Forest: An ensemble method that excels in handling overfitting, capable of managing large datasets with higher dimensionality without sacrificing model accuracy.

After a thorough assessment based on accuracy, the Random Forest model emerged as the superior choice. To optimize its performance, I conducted a grid search to determine the best hyperparameters, which revealed that a max_depth of 20 and n_estimators (number of trees in the forest) of 200 were ideal. These parameters strike a balance between model complexity and the risk of overfitting, leveraging the strength of Random Forest in creating an ensemble of deep trees without being overly specific to the training data.

Equipped with these optimized parameters, I proceeded to train the Random Forest model on the entire dataset. This approach aimed to leverage the full breadth of available data, thereby enhancing the robustness of the model. By harnessing the entire dataset, the model benefits from a more comprehensive learning process, potentially capturing subtler patterns and relationships within the data that might have been overlooked in a smaller sample.

## Results and Analysis

Upon training the Random Forest Classifier, it was used to make predictions on the X_test dataset. The  performance metrics were analyzed, including accuracy, precision, recall, and the F1 score. The model showcased a high accuracy of 0.89, indicative of its overall effectiveness in correctly classifying instances. However, a more nuanced understanding of its performance emerged upon examining the precision (0.72) and recall (0.93) scores, alongside an F1 score of 0.82.

The significantly higher recall compared to precision suggests that the model is exceptionally adept at identifying most of the relevant cases (true positives). A recall of 0.93 means the classifier successfully captures 93% of the actual positive instances. However, the lower precision score of 0.72 indicates that among the instances it classifies as positive, only 72% are actually positive. This discrepancy could imply a tendency of the model to have a higher rate of false positives – predicting some negative instances as positive.

The F1 score, being a reasonable mean of precision and recall, provides a balanced view of the model's performance. An F1 score of 0.82 indicates that the model achieves a decent balance between recall and precision, despite the disparity between them.

In summary, while the model demonstrates high accuracy and recall, indicating its capability to identify most positive cases, the relatively lower precision suggests room for improvement in reducing false positives. This analysis underscores the importance of considering multiple metrics beyond accuracy to gain a comprehensive understanding of a classifier’s performance, particularly in the context of the problem's specific needs and constraints.

## Conclusion and Discussion

A few challenges that I encountered during this project was dealing with an extremely large dataset along with complex machine learning models. To combat this I used a smaller sample size to do some of the analysis, but this still involved a lot of waiting. Overall, this project demonstrates a lot of potential. By successfully classifying Reddit posts into their respective subreddits, this project not only highlights the effectiveness of Natural Language Processing in content classification but also exhibits its application in broader digital content management and analysis. Such a classifier can be instrumental in areas like content moderation, trend identification, and user engagement analysis, offering invaluable tools for both social media platforms and marketers. The insights gained from this project underscore the transformative impact of machine learning in interpreting and organizing vast amounts of data in the digital age.

---

To get started with this project, clone the repository and install the necessary dependencies. If you have any questions or would like to contribute to the project, please feel free to open an issue or submit a pull request.

