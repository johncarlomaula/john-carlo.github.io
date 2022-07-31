# Predicting Customer Churning with Logistic Regression

**Project Description:** In this project, I explored a dataset about customer churning and built a logistic regression model to predict whether or not a customer will unsubscribe from a company's service.

<img src="images/project5_images/churn.png?_raw=true"/>

The Telco Churn dataset contains information about the customers of Telco, a telecommunications company that offers internet and phone service, and whether or not they “churned”. Churning is defined as leaving the company (i.e. unsubscribing from their services) within the last month. The dataset also contains information about a customer’s demographic and account information. 

The goal of this project is to build a logistic regression model that will predict whether or not a customer will cancel their services based on their features.

### Exploratory Data Analysis

After examining and viewing the dataset, I performed any necessary data cleaning that resulted in a finalized dataset containing 1995 rows and 20 columns. I explored the relationships between the predictors and churning. fter data cleaning, the finalized training set contains 1995 observations with 20 variables. The response variable, **churn**, has a prevalence of 27.3%.My important findings will be summarized below. For more details, on EDA, check out the notebook [here](https://github.com/johncarlomaula/telco-churn-project/blob/main/telco_eda.md).

**Key Findings:**

- Customers who have a higher monthly charge and lower tenure tend to churn more.
- Customers who are not senior citizens, have partners, have dependents, or don't use electronic checks are less likely to churn.
- Although customers with the *Fiber Optic* internet service are more likely to churn, it's due to the higher cost of that specific service rather than the quality of its services.
- Customers with online security, online backup, device protection, and tech supportare less likely to churn regardless of the cost and type of internet service. 

### Data Modeling

From the EDA, I determined the following predictors 

1. **Dependents**
2. **Monthly Charges**
3. **Monthly Contract** - whether or not a customer has a *month-to-month* contract
4. **Electronic Check** - whether ot not a customer's payment method is *electronic check*
5. **Has Service** - whether or not a customers has at least one of the following: *online security*, *online backup*, *device protection*, or *tech support*

The methodology I used can be summarized below. Using

<img src="images/project5_images/methodology.png?_raw=true"/>

The results of the models are summarize in the graph below.

<img src="images/project5_images/performance.png?_raw=true"/>




