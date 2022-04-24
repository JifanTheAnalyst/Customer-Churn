# Customer-Churn

# Business Background

PowerCo is a major gas and electricity utility who are considering offering a 20% discount to dissuade clients from churning as it'a fair hypothesis that price changes affect customer churn. Before implementing this strategy, it's necessary to test if price sensitivity is a main driver of customer churn. If it is, then a 20% discount could be an effective customer retention strategy.

# Objectives

1. Test hypothesis: **Is churn driven by the customers' price sensitivity?**
2. Build a predictive model for customer churning and evaluate the model
3. Examine the impact of a 20% discount on business

# Data Source and Understanding

- Data are provided by PowerCo. More descriptions are included in the 'Data' folder.
- Client data includes their historical and forecast electricity and gas consumption, contract related dates, etc.
- Price data include fixed and variable pricing in off-peak/mid-peak/peak period. 
- Churn indicator: whether each customer has churned or not.

# Framework and Method

1. Exploratory Data Analysis:

- Apply data visulaisation to gain a holistic understanding of data set (e.g. data statistics and variable distribution).
- Test if price (generally) is correlated with churn.

2. Feature Engineering:

- Create price sensivity features: 
  - Price differences across an entire year
  - Max price difference between months
  - Price differences across different time periods (off_peak, peak, mid_peak)
- Transform date features, categorical features and skewed features

3. Modelling:

- Logistic regression
- Random forest
- Predict churn and churn probability
- Evaluation: classification metrics and feature importance

4. Discount Impact:

- Revenue comparison of discount scenario and non-discount scenario
- Explore who should be given a discount to maximize profit
  - Depending on churn
  - Depending on churn and value of customer
  - Depending on churn probability
 
# Results


- **Price sensitivity is not a main driver but a weaker contributor.**
- **The current set of features are not discriminative enough to clearly distinguish between churners and non-churners.**
- **Giving discounts can be profitable to some level under assumptions.**

Churning clients account for 10%:

![churning status](https://user-images.githubusercontent.com/93923656/164960710-aa1fcbf6-4dea-40eb-9492-272ebc8bb188.png)

The correlation between price and churn is low:

![correlation](https://user-images.githubusercontent.com/93923656/164960712-2a88d34f-398f-4f44-8688-d8ac5260aae7.png)

The feature importance of price sensitivity features are scattered around:

![feature importance](https://user-images.githubusercontent.com/93923656/164960714-d7bce3ff-8913-41b6-ba80-a7f859e96516.png)

If we give discounts to clients with churn probability above 0.5, then profit is maximized and larger than not offering discounts:

![cutoff](https://user-images.githubusercontent.com/93923656/164964558-a39a5849-3011-4ee2-9387-d8dc38b7acb6.png)
# Recommendations


The generic 20% discount might not be effective. More personalised strategies need to be applied.

- Give different discounts according to churn probability.
- Find the discount level that balances customer retention vs the cost of false positives.

