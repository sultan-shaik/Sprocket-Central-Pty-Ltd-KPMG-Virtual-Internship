# Sprocket Central Pty Ltd company Customers Classification project - KPMG virtual internship: Project Overview




Sprocket Central Pty Ltd, a medium size bikes & cycling accessories organisation which has a large dataset relating to its customers, but their team is unsure how to effectively analyse it to help optimise its marketing strategy, the client provided me with four different datasets it's customers transactions,customers demographics and customers addresses, new potential customers dataset.

In this project i have managed to:

* Analyse the customers and reveal some important insights 

* Applied RFM segmentation to segment customers into four different segments (Platinum,Gold,Silver,Bronze)

* Created a model that used the existent customers features to train a Classification model (with 99% accuracy)

* Used the created model on a new customers dataset with similar features that predicted what type each new customer would be 

# Code and Resources Used

**Python Version:** 3.7

**Packages:** Pandas,numpy,sklearn,matplotlib,seaborn


# Data Cleaning:

The client as i mentioned has provided me with three datasets at the beginning (customers transactions,customers demographics,customers addresses) which i has to clean before start analyzing it for trends, i made the following changes:

# Customers Transactions Dataset

* Converted the types of list price,standard cost columns from object to numeric.
* Converted The Transactions date column from object into datetime
* online_order,brand, product line,product class,product size,standard cost and product_first_sold_date had null values which we ammended
* product_first_sold_date column had a wrong date format which we ammended
* Extracted year,month name,day,day name columns from transaction date column


# Customer demographics Dataset
* Converted past_3_years_bike_related_purchases,tenure from object into numeric
* Converted DOB column from object into datetime
* last_name,DOB,job_title,job_industry_category,default,tenure columns had null values which we ammended
* Extracted Age column from DOB column


# Customer address dataset
* Removed the Country column which represented one value only (Australia) since it will not be useful in my analysis nor in my ML model


# EDA analysis:
After finishing Data cleaning i joined the three data sets together into one big dataset and conducted an Exploratory data analysis on them and found the following insights

Univariate Analysis:

1. From the distribution of prices we notice that we have a normally distributed data with no outliers the average of the prices is 1106.
2. For Standard cost We have a positively skewed (right-skewed) distribution with some outliers, the average of the cost in dollars is 555.
3. Ages in the data are mostly distributed between 20s and 60s, the most demanding age of our customers range from 30 to mid 40s which makes sense since they are in the peak of their youth and trying to mantain their health and excercise more, the average age is 43.
4. purchases related to bikes is the purchases made by our customer in the past three years related to bikes , we have a normally distributed data with no outliers,the mean of the purchases in the past three years is 48.
5. The amount of orders along the year is almost the same but the highest time in the year is in the start and end of the summer in months July,August & October the reason for that could be that people are buying bikes to spend the summer vacation with.
6. althought the amount of bikes sold along the week is almost the same but we can identify a increase of amount on wednesday.
7. (Mass customers) represents 50% of the orders,(Affluent customers) represents 24% of the orders,(High net worth customers) represents 25% of the orders.
8. Most of our orders are done in NSW state in Ausrtalia since it has 50% of our orders.
9. Distribution of orders between men and women are almost the same , 51% of our orders are from women and 49% are from men.
10. Most of our customers work at manufacturing industry.

Bivariate Analysis:

1. Women who owns a car buy more bikes than women who don't and Men who do not own a car buy more than Men who do.
2. In most of the states women buy more than men but in Victoria and new south wales men buy more.
3. women order bikes online more than men.
4. Most profitable product from our products is WeareA2B brand

Mulitvariate distributions:

1. Most of the revenue has been produced by mass customers by males.
2. Manufacturing industry produced more revenue than other industries by male customers.
3. There are no strong correlations among numerical data.


Unusual distributions:

1. The Age had some outliers that we removed.
2. Standard cost had some outliers that we removed.


# RFM analysis

* I have conducted a RFM Model and segmented customers into four different segments (Platinum,Gold,Silver,Bronze)

* The RFM model is based on three quantitative factors:
1. Recency: How recently a customer has made a purchase
2. Frequency: How often a customer makes a purchase
3. Monetary Value: How much money a customer spends on purchases


*  As we can see there is a +ve relationship between Frequency and Monetary which means that our data is consistant

![image](https://github.com/sultan-shaik/Sprocket-Central-Pty-Ltd-KPMG-Virtual-Internship/assets/120010630/bf0dd2aa-a23f-459b-9f61-8700fc59e1c9)


* There is also a -ve relationship between Recency and Monetary , which shows that the higher the period is for the recent purchase of a customer the lower the money value he flows in the company

![image](https://github.com/sultan-shaik/Sprocket-Central-Pty-Ltd-KPMG-Virtual-Internship/assets/120010630/36391a52-6f73-4b6f-a21f-5c15a46827a7)


# Model Building:

* First i selected specific features to use in training the model, then i converted the categorical features into binary format (One Hot encoding for the nomial categorical variables & Label encoding for the ordinal categorical variables)
* I used a DecisionTreeClassifier & Random Forest classifier which were very useful for this kind of data, both of them gave me a 99% accuracy 
* I used the model on the (new customers dataset) provided by the company to precit what is the type of each new customer would be
