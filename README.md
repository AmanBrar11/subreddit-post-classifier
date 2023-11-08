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

The Reddit Post Classifier serves as a robust proof-of-concept that NLP and machine learning can be harnessed to generate meaningful categorizations of text data. I hope you find this project informative and inspiring for your data science endeavors!

---

To get started with this project, clone the repository and install the necessary dependencies. If you have any questions or would like to contribute to the project, please feel free to open an issue or submit a pull request.

