# Predicting Customer Churning with Logistic Regression

**Project Description:** In this project, I explore and analyze a dataset containing information about customers of a telecommunications company. Then, I build a logistic regression model to predict whether or not a customer will unsubscribe from the company, also known as "churning".

<img src="images/project5_images/churn.png?_raw=true"/>

The Telco Churn dataset contains information about the customers of Telco, a telecommunications company that offers internet and phone service, and whether or not they “churned”. Churning is defined as leaving the company (i.e. unsubscribing from their services) within the last month. The dataset also contains information about a customer’s demographic and account information. 

The goal of this project is to build a logistic regression model that will predict whether or not a customer will cancel their services based on their features.


### Exploratory Data Analysis

The data has been split into two sets: training set and testing set. Each set has 2000 rows and 21 variables. After data cleaning, the finalized training set contained 1995 rows and 20 variables with a churning prevalence of 27.3%. My key findings are summarized below: 

- Customers who have a higher monthly charge and lower tenure tend to churn more (fig 1).
- Customers who are not senior citizens, have partners, have dependents, or don't use electronic checks are less likely to churn (fig 2).
- Customers with online security, online backup, device protection, and tech support are less likely to churn regardless of the cost and type of internet service (fig 3 and fig 4). 
- Although customers with the *Fiber Optic* internet service are more likely to churn, it's due to the higher cost of that specific service rather than the quality of its services.

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

1. Changing the probability threshold to the optimal cutoff (fig 5).
2. Bootstrapping to achieve a 50% churning prevalence in the dataset. 

Then, I will use the validation set to measure its final performance. The methodology can be summarized in the image below.

<img src="images/project5_images/methodology.png?_raw=true"/>


### Model Results

The results of the model performance are summarized in the table below. It's also visualized in Figure 6 in the appendix. 

| Metric | Optimal Cutoff | Bootstrapped Model |
| --- |  :---------: | :---------: |
| Accuracy| 65.9% | 69.6% |
| Sensitivity | 80.7% | 72.3% |
| Specificity | 60.0% | 68.6% |

Both models have a lower accuracy than the initial model, but they have a higher sensitivity. Since the bootstrapped model has a higher overall accuracy and specificity, I decided to choose that model has a the final model. However, depending on the costs of customer retention vs the cost of losing a customer, the other model might be better due to its higher sensitivity. 

For example, if the loss of a customer is more costly than the cost of any implemented customer retention strategies, then this model will be a better option since it ensures that customers who are more likely to churn are identified.

On the other hand, if the cost is about the same, then the bootstrapped model will be a better option since it ensures that as many customers are correctly classified regardless of whether or not they are more likely to churn.

### Feature Importance

Feature importance is a measurement of how important or influential a variable is in predicting churning. One way of measuring influence is by examining the coefficients of the logistic regression model.

For example, **monthly contract** has a coefficient of 1.977 in the model. This means that customers with a monthly contract have a **622% increase** in the odds of churning compared to those who have a 1-year or 2-year contract when all other variables are kept constant. 

All predictors included in the model were determined to be important in predicting churning. 

### Actionable Insights

- Focus on customers who have a monthly contract. Offer incentives when signing up for a 1-year or 2-year contract.
- Overhaul the *Fiber Optic* internet service. It has a higher overall monthly cost, but there does not appear to be a difference in the quality of the services provided when compared to *DSL*. 
- Examine the electronic check payment channel. If extra costs are are associated with this kind of payment, find a way to decrease it. Another option is to make other methods more convenient.
- Properly inform customers about the offered services such as online protection, online backup, etc. and their benefits.

## Appendix - Images



<img src="images/project5_images/boxplots.png?_raw=true"/>

**Figure 1** - Boxplots of tenure, monthly charges, and total charges against churning.

<img src="images/project5_images/binary.png?_raw=true"/>

**Figure 2** - Barplots of binary variables such as dependents, senior citizenship, etc. against churning.

<img src="images/project5_images/dsl_optic_churn.png?_raw=true"/>

**Figure 3** - Barplots of the provided services against churning of the two types of internet services, *DSL* and *Fiber Optic*.

<img src="images/project5_images/dsl_fiber_mc.png?_raw=true"/>

**Figure 4** - Barplots of the provided services against monthly charges of the two types of internet services, *DSL* and *Fiber Optic*. 

<img src="images/project5_images/roc.png?_raw=true"/>

**Figure 5** - Left: distribution of predicted probabilities under each class. Right: ROC curve with the location of the optimal cutoff point. 

<img src="images/project5_images/performance.png?_raw=true"/>

**Figure 6** - Plot of the model performance of all the models from the testing and validation sets.


