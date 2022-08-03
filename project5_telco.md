# Predicting Customer Churning with Logistic Regression

**Project Description:** In this project, I explore and analyze a dataset containing information about customers of a telecommunications company. Then, I build a logistic regression model to predict whether or not a customer will unsubscribe from the company, also known as "churning".

<img src="images/project5_images/churn.png?_raw=true"/>

The Telco Churn dataset contains information about the customers of Telco, a telecommunications company that offers internet and phone service, and whether or not they “churned”. Churning is defined as leaving the company (i.e. unsubscribing from their services) within the last month. The dataset also contains information about a customer’s demographic and account information. 

The goal of this project is to build a logistic regression model that will predict whether or not a customer will cancel their services based on their features.


### [Exploratory Data Analysis](https://github.com/johncarlomaula/telco-churn-project/blob/main/telco_eda.md)

The data has been split into two sets: training set and testing set. Each set has 2000 rows and 21 variables. After data cleaning, the finalized training set contained 1995 rows and 20 variables with a churning prevalence of 27.3%. My key findings are summarized below: 

- Customers who have a higher monthly charge and lower tenure tend to churn more (fig 1).
- Customers who are not senior citizens, have partners, have dependents, or don't use electronic checks are less likely to churn (fig 2).
- Customers with online security, online backup, device protection, and tech support are less likely to churn regardless of the cost and type of internet service (fig 3 and fig 4). 
- Although customers with the *Fiber Optic* internet service are more likely to churn, it's due to the higher cost of that specific service rather than the quality of its services.

Based on my findings from EDA, I determined 2 variables that will be useful in predicting churning: **dependents** and **monthly charges**. In addition, I created 3 new features using variables from the dataset:

1. **Monthly Contract** - whether or not a customer has a *month-to-month* contract
2. **Has Service** - whether or not a customer has at least ONE of the following variables: *online security*, *online backup*, *device protection*, and *tech support*
3. **Electronic Check** - whether or not a customer's payment method is *electronic check*

Thus, a total of 5 predictors will be used to build the model.

### [Data Modeling](https://github.com/johncarlomaula/telco-churn-project/blob/main/telco_model.md)

Due to the binary nature of the response variable, I decided to use logistic regression to build my predictive model. I used the testing set to measure its performance, which resulted in a **79.0% accuracy**. While the accuracy is pretty good, the model has a low **sensitivity of 46.9%**. This means that more than half of customers who churned were misclassfied.

Thus, I decided to improve the model in two different ways:

1. Changing the probability threshold of classification to maximize sensitivity and specificity.
2. Bootstrapping samples to achieve a balanced dataset (i.e. 50% prevalence in churning). 

Then, I will use the validation set to measure its final performance. The methodology can be summarized below.

<img src="images/project5_images/methodology.png?_raw=true"/>

The results of the model performance are summarized in the table below. It's also visualized in Figure 6 in the appendix. 

| Metric | Optimal Cutoff | Bootstrapped Model | Difference |
| --- |  :---------: | :---------: | :---------: |
| Accuracy| 65.9% | 69.6% | +3.7% |
| Sensitivity | 80.7% | 72.3% | -8.4% |
| Specificity | 60.0% | 68.6% | +8.6% |

Both models have a lower accuracy than the initial model, but they both have higher sensitivity. Since the bootstrapped model has a higher accuracy (+3.7%) and specificity (+8.6%), I decided to select that model as the final model. Compared to the original model, the bootstrapped model has a **54.2% greater performance** in correctly identifying customers who will churn. 

All predictors included in this model were determined to be important in predicting churning, with monthly contract being the most influential predictor. Customers who have this type of contract have a **622% greater** odds of churning.

### Recommendations

While the bootstrapped model is my recommended final model, the other model might be better if the cost of losing a customer greater than the cost of implementing customer retention stragies due to its higher sensitivity. 

Overall, I recommend the following actions to be done:

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


