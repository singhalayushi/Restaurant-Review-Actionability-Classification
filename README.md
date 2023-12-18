## Introduction

Restaurant managers today rely heavily on customer reviews to improve their businesses. However, sifting through vast amounts of online reviews to identify actionable feedback can be a time-consuming and tedious task. This project explores the use of machine learning to automate the process of identifying actionable customer reviews, empowering restaurant managers to make data-driven decisions and improve customer satisfaction.

## Data Sources and Processing

The dataset used in this project consists of reviews for the Dal Rae restaurant in Pico Rivera, California, sourced from OpenTable and Yelp. A total of 7,060 reviews were web-scraped using Python libraries like BeautifulSoup and Selenium.

To accurately label each review as actionable or not actionable, we utilized the OpenAI API to employ the gpt-3.5-turbo LLM. However, limitations in API rate limits and model stochasticity led us to create two datasets:

Full Dataset: Labeled by gpt-3.5-turbo with a single query.
Identical Classification Dataset: Contains reviews classified consistently by gpt-3.5-turbo across five trials.
Both datasets were subjected to data cleaning and preprocessing, including removal of punctuation, lowercase conversion, and tokenization.

## Model Development and Evaluation

We explored three machine learning models for determining review actionability:

Logistic Regression: Baseline model with L2 regularization.
Random Forest Classifier: Baseline model with hyperparameter tuning.
Deep Neural Network: Four-layer DNN with L2 and dropout regularization.
We utilized accuracy, precision, recall, F1 score, confusion matrix, ROC curve, AUC, and perplexity for evaluation.

## Results and Discussion

All three models achieved similar test accuracy on the full dataset (77% - 85%).
The DNN exhibited higher accuracy (85.33%) on the identical classification dataset but suffered from lower precision and F1 score due to gpt-3.5-turbo's stochasticity.

![image](https://github.com/singhalayushi/Restaurant-Review-Actionability-Classification/assets/123263574/52c2a566-53dd-4876-ae18-88bab72af70b)


Topic modeling using LDA identified seven distinct themes present in the reviews, providing further insights into customer feedback.

Word cloud showing the most frequently used words:
![image](https://github.com/singhalayushi/Restaurant-Review-Actionability-Classification/assets/123263574/5f5efac5-7d80-43b3-8eb4-d6f8e0bc25d0)

Intertopic Distance Plot that helps understand the relation and the distance between topics:
![image](https://github.com/singhalayushi/Restaurant-Review-Actionability-Classification/assets/123263574/ec8712bd-77e0-4ee9-ba68-484dea82b428)

Results from Summarizer
![image](https://github.com/singhalayushi/Restaurant-Review-Actionability-Classification/assets/123263574/c0982c0f-d743-4943-aca2-5129310c2f12)

Topic Modelling Results:
![image](https://github.com/singhalayushi/Restaurant-Review-Actionability-Classification/assets/123263574/c6694cf8-874c-4193-9176-3273d4267755)


## Conclusion

While limitations in gpt-3.5-turbo's accuracy limited the overall model performance, our project successfully developed machine learning models to automate the identification of actionable customer reviews. This provides restaurant managers with a valuable tool to analyze customer feedback more efficiently and make data-driven decisions for improving their business.
