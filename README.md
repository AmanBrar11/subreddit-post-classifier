# Subeddit Post Classifier

## Introduction

Welcome to my GitHub repository for my Subreddit Post Classifier project. This project aims to process and analyze a massive [dataset](https://github.com/linanqiu/reddit-dataset) containing over 200,000 posts from various subreddits. By applying machine learning techniques, specifically a Random Forest Classifier, we are able to predict the subreddit category for given text posts with high accuracy. 

## Purpose

The purpose of this project is twofold: firstly, to demonstrate the power of Natural Language Processing (NLP) and machine learning in classifying text data, and secondly, to provide a practical tool that can automatically categorize Reddit posts. This has numerous applications, from content filtering and recommendation systems to social media monitoring and data analysis.

## Importance

In the age of information overload, the ability to automatically sort and classify vast amounts of text data is invaluable. Not only does it aid in managing the data, but it also enables the extraction of insights and trends from specific communities. This project showcases how a relatively simple machine learning model can provide a high degree of accuracy in text classification tasks, paving the way for more complex and nuanced data analysis.

## Real-World Applications

This classifier can be employed in various real-world scenarios such as:

- **Content Moderation:** Automatically flagging or categorizing posts for review to maintain community standards.
- **Marketing Insights:** Analyzing customer sentiment and interests across different subreddit communities for targeted marketing.
- **Trend Analysis:** Monitoring the popularity and discussion topics within communities over time to identify trends.
- **Custom Feeds:** Creating personalized content feeds for users based on their interests.

## Process

The process of creating the classifier included several steps:

1. **Data Collection:** The dataset was sourced from a public GitHub repository containing Reddit posts from 50 subreddits.
2. **Data Preprocessing:** This involved cleaning the text data by removing special characters and numbers, lowering the case, eliminating stop words, lemmatizing, and removing short tokens.
3. **Feature Engineering:** Text data was converted into numerical data using TF-IDF vectorization to prepare it for machine learning models.
4. **Model Training:** A Random Forest Classifier was trained with hyperparameter tuning using GridSearchCV to find the optimal settings.
5. **Evaluation:** The model was evaluated on a test set, resulting in an accuracy of approximately 89.46%.
6. **Prediction:** A function was created to predict the subreddit category for new Reddit post texts.

Feel free to explore the Jupyter Notebook included in this repository for a detailed look at the code and methodology.

## Conclusion

The Reddit Post Classifier has successfully demonstrated that NLP coupled with machine learning can effectively categorize text data with a high degree of accuracy. By meticulously preprocessing the text data—cleaning, normalizing, and transforming it into a suitable format for analysis—and then leveraging the power of a Random Forest Classifier, this project was able to achieve an accuracy of 89.4%.

This level of accuracy is significant, especially considering the diverse and colloquial nature of language used across different Reddit communities. The classifier's performance is a testament to the careful feature engineering using TF-IDF vectorization, which captures the importance of words in relation to their context in the entire dataset, and the robustness of the Random Forest algorithm, which works well for varied datasets by constructing multiple decision trees and outputting the mode of their predictions.

The fine-tuning of hyperparameters through GridSearchCV played a crucial role in enhancing the model's predictive capabilities. By systematically searching for the optimal combination of parameters such as the number of trees in the forest (`n_estimators`) and the maximum depth of the trees (`max_depth`), the model was not only able to learn effectively from the training dataset but also generalize well to unseen data, which is evident from its test performance.

In summary, the achieved accuracy underscores the potential of this classifier to be adapted for broader NLP tasks and reflects the quality of the methodology adopted in this project. It is a significant stride in text classification and provides a solid foundation for further exploration and development. I welcome fellow developers and data enthusiasts to build upon this project, improve the classifier's accuracy, and adapt it to other datasets or similar tasks. Your insights and contributions are highly appreciated, and together, we can push the boundaries of what's possible with machine learning in natural language processing.

---

To get started with this project, clone the repository and install the necessary dependencies. If you have any questions or would like to contribute to the project, please feel free to open an issue or submit a pull request.

