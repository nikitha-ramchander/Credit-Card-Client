# Credit Card Clients

This dataset contains information on default payments, demographic factors, credit data, history of payment, and bill statements of credit card clients in Taiwan from April 2005 to September 2005. My goal is to find out how the probability of default payment vary by categories of different demographic variables and 
which variables are the strongest predictors of default payment?

---------------

#### Objectives:  
1. Exploratory Data Analysis 
>Data Cleaning

> Data Visualizations  
2. Build Machine Learning Models 
>Logistic Regression

>Random Forests 
3. Provide Recommendations 

---------------

#### Data Cleaning
>Using python I loaded the data set and imported libraries, Pandas, and Numpy to start exploring the data. The first few steps required validating data types and checking syntax errors. Pleased to say the all data types were consistent, and there were no missing values. The first change I made in my dataset was renaming the target column from 'default.payment.next.month' to 'Default_Payment'. From there I noticed inconsistencies in the 'Marriage' and 'Education' columns. In the marriage column there are 4 assigned categories to marital status:(1=married, 2=single, 3=others, 0 = unknown). I decided to group 0 under 3 because an unknown category is irrelevant when modeling. Similarly in the education column there are 7 assigned categories: (1=graduate school, 2=university, 3=high school, 4=others, 5=unknown, 6=unknown). I decided to group 4, 5, and 6 under 4 because an unknown category is irrelevant when modeling. Last step in my data cleaning was setting ID as the index. 

#### Data Visualizations
>I came up with a few graphs that helped me better understand the data. 

![Pic 1](https://user-images.githubusercontent.com/77766107/115168666-91ede380-a070-11eb-8ebd-39e713383220.png)
>In general more people have lower credit limits. There is a high amount of people that have and haven’t defaulted payment in the lower limit balance.

![Pic 2](https://user-images.githubusercontent.com/77766107/115168703-aaf69480-a070-11eb-8ca9-b6a68fc0f9ae.png)
>A few findings: The probability of Men defaulting their payment is higher than Women. Higher the education, the lower the probability of defaulting payment next month. The probability of Married couples defaulting their payments is higher than Single.

![Pic 3](https://user-images.githubusercontent.com/77766107/115168773-e002e700-a070-11eb-999d-2371c45b3f12.png)
>This graphs shows the repayment status and bill amount for the month of September 2005. Credit card clients that delay their payment for two months and more are more likely to default their payment for the next month.

![Pic 4](https://user-images.githubusercontent.com/77766107/115168765-db3e3300-a070-11eb-938c-f41768cad7de.png)
>This graph shows the repayment status and bill amount for the month of April 2005. Similarly to the graph above credit card clients that delay their payment for two months and more are more likely to default their payment for the next month.

![Pic 5](https://user-images.githubusercontent.com/77766107/115168782-e98c4f00-a070-11eb-89c1-def7c004c189.png)

#### Machine Learning Model 
>From the two different Machine Learning Models implemented, Random Forests produced the highest Training Accuracy of 81%. I ran classification metrics of Sensitivity, Specificity, Precision, and AUC ROC. It depends on the credit card compnies goal and which metric they want focus in on. For example, if the company wants to make sure they’re only approving loans for people that will pay them back then they will focus on Precision. Precision score was 63% meaning you are 63% correct for clients that you do predict will default. I also looked at the important features in this model which was Pay_0, Age, and BILL_AMT1. These three features were also the most important in Logistic Regression.

![Pic 6](https://user-images.githubusercontent.com/77766107/115169143-0f662380-a072-11eb-95cb-8645d282ef3e.png)

#### Recommendations
> Overall, I believe we need to gather more realistic information from credit card clients. Besides the dataset including demographic variables there were alot of columns involving how much they currently owe in their bank account. Before issuing credit card we should verify their salary and based upon that give an appropriate credit limit. We should also consider whether clients are using these credit cards for basic necessities like gas or groceries or are they big spenders and thats why they aren't able to make their payments on time. Next we need to discuss some strategic initiatives that we could do to prevent people from delaying their payment 2 months or more. By giving out positive incentives such as clients that dont default another month then they will recieve double cashback or double points. If tha doesnt work then we need to enforce a negative policy stating people that default their payment another month they will pay doublt the late payment fee and it will keep going up every month they default from the first.
