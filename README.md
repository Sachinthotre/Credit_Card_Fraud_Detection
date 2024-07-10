# Credit Card Fraud Detection model based on anonymized credit card transactions

This project is divided into two main sections:
1. **Data Analysis**
2. **Machine Learning for Fraud Detection**

#  **Data Analysis**
It is important that credit card companies are able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase.

In this Data Analysis project section, I explored Kaggle datasets related to credit card spending habits in India and demonstrated how to utilize these datasets in Power BI. You can download the working file available, and the Kaggle dataset link is in the description. After importing the CSV file into Power BI, I performed data profiling, cleaned the data, and split columns where necessary. I created a date table with calculated columns for year, month number, and month name to facilitate time intelligence functions. Various visualizations were created, including slicers for year/month, gender, card type, and expense type, as well as charts and graphs like 100% stacked bar charts, donut charts, treemaps, line charts, and box plots. Additionally, I used field and numerical range parameters to create dynamic reports, including a top-N cities report with a custom measure for ranking. The project showcases comprehensive data visualization and analysis techniques in Power BI, providing insights into credit card spending patterns.

![Screenshot 2024-07-08 191044](https://github.com/Sachinthotre/Credit-card-Fraud-detection/assets/46932228/0efcdc16-cd64-43a4-b044-fc248b1eafd6)


#  **Machine learning section**
Credit card fraud is a significant concern for financial institutions and consumers alike. With the rise of online transactions, detecting fraudulent activities has become increasingly challenging. This project aims to build a robust fraud detection system using Python and popular machine learning libraries such as scikit-learn.

## Overview

In this project, I have performed the following:

- **The Importance of Fraud Detection**: Understanding the impact of credit card fraud on financial security.
- **Preprocessing Techniques**: Handling imbalanced datasets commonly encountered in fraud detection tasks.
- **Machine Learning Algorithms**: Implementing various models such as Logistic Regression, RandomForestClassifier, GradientBoostingClassifier, and LinearSVC for fraud detection.
- **Model Evaluation**: Using metrics like precision, recall, and F1-score to evaluate the performance of the models.
- **Model Fine-Tuning**: Improving the performance and reliability of the models through fine-tuning.

  
# Business Understanding

## Project Components

1. **Data Analysis and Understanding**:

#Business Understanding

Credit Card Fraud Detection is a classic class-imbalance problem where the number of fraud transactions is much lesser than the number of legitimate transaction for any bank. Most of the approaches involve building model on such imbalanced data, and thus fails to produce results on real-time new data because of overfitting on training data and a bias towards the majoritarian class of legitimate transactions. Thus, we can see this as an anomaly detection problem. 

1. What time does the Credit Card Frauds usually take place?
2. What are the general trends of amounts for Credit Card Fraud Transactions?
3. How do we balance the data to not let the model overfit on legitimate transactions?

#Analysis
The Dataset we use is the Kaggle Credit Card Fraud Detection Dataset enlisted in the following link: <a href="https://www.kaggle.com/mlg-ulb/creditcardfraud">Link</a>

- The Data has 32 features from V1-V28 which are unknown for confidentiality, TIme, Amount and Class
- The input features are V1-V28, Time and Amount
- The target variable is Class
- The Data does not have any missing values as evident from the code, thus need not be handled
- The Data consists of all numerical features, and only the Target Variable Class is a categorical feature.
    - Class 0: Legitimate Transaction
    - Class 1: Fraud Transaction

    - Analyzing the dataset to gain insights into the features and target variable.
    - Understanding the distribution of classes (fraud vs. non-fraud) and the challenges of imbalanced data.

3. **Data Preparation**:
    - Techniques for preparing data, including handling missing values, scaling features, and encoding categorical variables.
    - Methods to address class imbalance, such as oversampling, undersampling, and Synthetic Minority Over-sampling Technique (SMOTE).
    - The Data does not have any missing values and hence, need not be handled.
    - The Data has only Target Variable Class as the categorical variable.
    - Remaining Features are numerical and need to be only standardized for comparison after balancing the dataset
    - The mean of the amount of money in transactions is 88.34
    - The standard deviation of amount of money in transactions is 250.12
    - The time is distributed throughout the data equitably and hence, serves as an independent feature
    - It is best to not remove or drop any data or features in this case and try to tune the model assuming them as independent features initially


4. **Model Building**:
    - Implementing and training the following models:
        - **Logistic Regression**: A simple yet effective linear model for binary classification.
        - **K-Nearest Neighbors (KNN)**: A non-parametric method used for classification and regression.
        - **Decision Trees**: A model that uses a tree-like structure of decisions and their possible consequences.
        - **RandomForestClassifier**: An ensemble method that uses multiple decision trees to improve classification performance.
        - **GradientBoostingClassifier**: An optimized gradient boosting algorithm that provides high performance and efficiency.
        - **LinearSVC**: A linear support vector classifier that works well with large datasets.

5. **Model Evaluation and Metrics**:
    - Evaluating models using various metrics such as accuracy, precision, recall, F1-score, and AUC-ROC.
    - Understanding the trade-offs between precision and recall, especially in the context of fraud detection.

6. **Model Fine-Tuning**:
    - Techniques to improve model performance, including hyperparameter tuning and cross-validation.
    - Using GridSearchCV and RandomizedSearchCV to find the best model parameters.


### Conclusion
- The K-Nearest Neighbors Classifier tuned with Grid Search with the best parameter being the Euclidean Distance (p=2) outperforms its counterparts to give a test accuracy of nearly 99.8% and a perfect F1-Score with minimal overfitting
- SMOTE overcomes overfitting by synthetically oversampling minority class labels and is successful to a great degree

### Summary
- All Fraud Transactions occur for an amount below 2500. Thus, the bank can infer clearly that the fraud committers try to commit frauds of smaller amounts to avoid suspicion.
- The fraud transactions are equitable distributed throughout time and there is no clear relationship of time with commiting of fraud.
- The number of fraud transactions are very few comparted to legitimate transactions and it has to be balanced in order for a fair comparison to prevent the model from overfitting.

## Getting Started

To get started with this project, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/credit-card-fraud-detection.git
    cd credit-card-fraud-detection
    ```

2. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Run the Jupyter Notebook:
    ```bash
    jupyter notebook
    ```

4. Follow the steps in the notebook to preprocess the data, build the models, and evaluate their performance.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

By following this tutorial, you will gain a solid understanding of how to build and evaluate machine learning models for fraud detection. Happy coding!
