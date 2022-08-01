# Predicting Customer Churning with Logistic Regression

**Project Description:** In this project, I explore and analyze a dataset containing information about customers of a telecommunications company. Then, I build a logistic regression model to predict whether or not a customer will unsubscribe from the company, also known as "churning".

<img src="images/project5_images/churn.png?_raw=true"/>

The Telco Churn dataset contains information about the customers of Telco, a telecommunications company that offers internet and phone service, and whether or not they “churned”. Churning is defined as leaving the company (i.e. unsubscribing from their services) within the last month. The dataset also contains information about a customer’s demographic and account information. 

The goal of this project is to build a logistic regression model that will predict whether or not a customer will cancel their services based on their features.


### Exploratory Data Analysis

The data has been split into two sets: training set and testing set. Each set has 2000 rows and 21 variables. After data cleaning, the finalized training set contained 1995 rows and 20 variables with a churning prevalence of 27.3%. My key findings are summarized below: 

- Customers who have a higher monthly charge and lower tenure tend to churn more.
- Customers who are not senior citizens, have partners, have dependents, or don't use electronic checks are less likely to churn.
- Although customers with the *Fiber Optic* internet service are more likely to churn, it's due to the higher cost of that specific service rather than the quality of its services.
- Customers with online security, online backup, device protection, and tech supportare less likely to churn regardless of the cost and type of internet service. 

For more details on EDA, check out the R Markdown notebook [here](https://github.com/johncarlomaula/telco-churn-project/blob/main/telco_eda.md).

### Feature Engineering

Based on my findings from EDA, I determine 2 variables that will be useful in predicting churning: **dependents** and **monthly charges**. In addition, I created 3 new features using variables from the dataset:

1. **Monthly Contract** - whether or not a customer has a *month-to-month* contract
2. **Has Service** - whether or not a customer has at least ONE of the following variables: *online security*, *online backup*, *device protection*, and *tech support*
3. **Electronic Check** - whether or not a customer's payment method is *electronic check*

Thus, a total of 5 predictors will be used to build the model.

### Data Modeling

I decided to build a logistic regression model due to the binary nature of the response variables, churning. This method involves modeling the log-odds of churning, from which I can derive the probability that a customer will churn. With the predicted probability values, I can classify customers as churning or not churning. 

Thus, I fit a logistic regression model with the 5 predictors on the training data. Then, I used the testing set to measure its performance:

| Metric | Value |
| --- | ----------- |
| Accuracy| 79.0% |
| Sensitivity | 46.9% |
| Specificity | 88.3% |

While the accuracy is decent, the model has poor sensitivity. More than half of the churning customers were incorrectly classified as not churning. 

### Improving the Model

Once I fit the initial model and measured its performance, I decided to improve its performance in two different ways:

1. Changing the probability threshold to the optimal cutoff
2. Bootstrapping to achieve a 50% churning prevalence in the dataset. 

Then, I will use the validation set to measure its final performance. The methodology can be summarized in the image below.

<img src="images/project5_images/methodology.png?_raw=true"/>


### Model Results

The results of the model performance are summarized in the graph below.

<img src="images/project5_images/performance.png?_raw=true"/>




