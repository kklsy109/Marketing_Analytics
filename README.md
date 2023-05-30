# Marketing_Analytics


## Table Of Content
[Project Dataset](https://www.kaggle.com/datasets/jackdaoud/marketing-data/versions/1)<br>

1. Introduction<br>
    1.1 Purpose of this Analysis<br>
    1.2 Understanding Datasets<br>
    1.3 Exploratory Data Analysis<br>
    1.4 Statistical Analysis<br>
    1.5 Data Visualization<br>
2. [Exploratory Data Analysis(EDA)](https://github.com/kklsy109/Marketing_Analytics/blob/main/Marketing_Analytics_EDA.ipynb)<br>
    2.1 load and view data<br>
    2.2 View default values and fill in default values<br>
    2.3 View outliers<br>
    2.4 Convert Format<br>
    2.5 Feature Engineering<br>
    2.6 Feature Correlation<br>

3. [Statistical Analysis](https://github.com/kklsy109/Marketing_Analytics/blob/main/Marketing_Analytics_Statistical_Analysis.ipynb)<br>
    3.1 Factors related to the number of store purchases<br>
    3.2 Analysis of purchase volume in different countries<br>
    3.3 Analyze the consumption of people who buy gold<br>
    3.4 See what factors affect fish purchases<br>
    3.5 Analyze the differences in the acceptance of campaigns in different countries<br>
4. [Data Visualization](https://github.com/kklsy109/Marketing_Analytics/blob/main/Marketing_Analytics_Data_Visualization.ipynb)<br>
    4.1 Campaign acceptance<br>
    4.2 Average Characteristics of Customers<br>
    4.3 Most Popular Product<br>
    4.4 Acceptance by different channels<br>
5. Conclusion<br>



### 1. Introduction
#### 1.1 Purpose of this Analysis
In this project, I will conduct Exploratory Data Analysis (EDA), statistical analysis, and data visualization on the dataset to gain insights into customer preferences and market trends. By doing so, I aim to provide crucial marketing recommendations to the company, assisting them in formulating effective marketing strategies and enhancing their market competitiveness.

#### 1.2 Understanding Datasets
The data set ‘marketing_data.csv’ consists of 2,240 customers of XYZ company with data on:

Customer profiles
Product preferences
Campaign successes/failures
Channel performance

#### 1.3 Exploratory Data Analysis
In this section, I will perform missing value treatment on the data, design meaningful variables for the given data, and exclude outliers. Visual analysis will be conducted based on the correlation between features.


#### 1.4 Statistical Analysis
In this section, I will perform statistical analysis on the data using regression and provide a more detailed analysis of the features.


#### 1.5 Data Visualization
In this section, I will visually demonstrate which marketing campaigns have been the most successful and which products have been more popular. This visualization will help the company understand customer data more effectively and formulate better marketing strategies.


### 2. Exploratory Data Analysis（EDA)

#### 2.1 load and view data

I first load and view the dataset, there are 28 columns

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/1.png)

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/2.png)

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/3.png)

I converted the income column to numeric format.

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/4.png)


#### 2.2 View default values and fill in default values

I checked the number of default values in each column and found that only the income column lacked 24 values.

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/5.png)

Draw a histogram of the income column

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/6.png)

fill the default value with the mean

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/7.png)

#### 2.3 View outliers

Plot boxplots to see outliers

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/8.png)

It can be seen that outliers appear in 'Year_Birth', I decided to remove these two outliers.

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/9.png)

#### 2.4 Convert Format

The 'Dt_Customer' attribute should be converted to datetime.

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/10.png)

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/11.png)

#### 2.5 Feature Engineering

Looking at the individual properties, I identified five characteristics that can be analyzed:

1.Children_number: total number of children in the family

2.Customer_Year: the year you became a customer

3.Total_Mnt: the total cost of purchasing various products

4.Total_Purchases: the number of all payments

5.Total_Campaigns: The total number of customer acceptance campaigns


![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/12.png)

#### 2.6 Feature Correlation

Plot a heat map between features to view correlations

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/13.png)

Heatmap can reveal three categories of related features:

1.Features positively correlated with 'Income': All features of 'Mnt' and 'Purchases' show a positive correlation with 'Income.' This means that the more income someone has, the greater the quantity and price of their purchases.

2.Features related to 'Children_number': All features of 'Mnt' and 'Purchases' show a negative correlation with 'Children_number.' This indicates that the more children someone has, the fewer items they purchase, and the lower the prices.

However, an exception is 'NumDealsPurchases,' which is positively correlated with 'Children_number.' 'Income' is negatively correlated with 'Children_number.'

3.Features related to activity acceptance: Activity acceptance has a strong correlation with 'Response'*(target). Activity acceptance has a weak positive correlation with 'Income' and a weak negative correlation with 'Children_number.'

Exception:

There is no correlation between 'NumWebVisitsMonth' and 'NumWebPurchases.' However, there is a positive correlation between 'NumDealsPurchases' and 'Children_number.


#### Perform visual analysis of the above analysis separately

1) 'Income'and 'Total_Mnt'

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/14.png)

It can be observed that there is a positive correlation between income and total spending. The higher the income, the higher the total expenditure.

2) 'Children_number'and 'Total_Mnt'

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/15.png)

It can be observed that there is a negative correlation between the number of children a customer has and the total spending. The more children they have, the less they spend.

3) 'Children_number' and 'NumDealsPurchases'

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/16.png)

It can be observed that there is a weak positive correlation between the number of children a customer has and the frequency of purchases. As the number of children increases, there is a slight increase in the number of purchases.

4) 'Total_Campaigns' and 'Income'

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/17.png)

It can be observed that there is a weak positive correlation between the frequency of customer participation in activities and income. As income increases, there is a slight increase in the number of times they participate in activities.

5) 'Total_Campaigns' and 'Children_number'

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/18.png)

It can be observed that the frequency of customer participation in activities does not show a significant correlation with the number of children they have.

6) 'NumWebVisitsMonth' and 'NumWebPurchases'


![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/19.png)

It can be observed that there is no significant correlation between customer web page click rate and the number of online purchases.

7) 'NumWebVisitsMonth' and 'NumDealsPurchases'

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/20.png)

It can be observed that there is a clear positive correlation between customer web click rate and the total number of purchases made by the customer.

### 3. Statistical Analysis

#### 3.1 Factors related to the number of store purchases

First remove the extraneous columns.

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/21.png)

Check the number of unique values each column has.

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/22.png)

You can see that there are 3 categorical variables, 'Education', 'Marital_Status' and 'Country'

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/23.png)

One-hot processing of categorical variables.

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/24.png)

Merge the one-hot processed data with the original data set.

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/25.png)

Fit a linear regression model to the training data (70% of the dataset)

Evaluate the predictions on the test data (30% of the dataset) using RMSE:

Isolate X and y variables, and split the dataset into two parts, train and test.

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/26.png)

Using feature importance ranking to identify significant factors affecting store purchase quantity.

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/27.png)

It can be concluded that there are 4 important factors that affect store purchases:

'Total_Purchases', 'NumCatalogPurchases', 'NumWebPurchases', 'NumDealsPurchases'

I explore the directionality of these effects using SHAP values:

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/28.png)

Through the shape graph, the following can be observed:

'TotalPurchases': The quantity of purchases made at the store increases with an increase in the total number of purchases.

'NumCatalogPurchases', 'NumWebPurchases', 'NumDealsPurchases': The quantity of purchases made at the store decreases with an increase in the number of catalog purchases, web purchases, or deal purchases.


#### 3.2 Analysis of purchase volume in different countries

Draw a bar plot of purchases in different countries

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/29.png)

Draw a bar plot of total cost in different countries

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/30.png)

According to the bar chart, it can be seen that the SP country has the largest purchasing power, followed by SA, CA.....

#### 3.3 Analyze the consumption of people who buy gold

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/31.png)

Use Kendall for correlation analysis

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/32.png)

It can be seen that the people who buy gold are positively correlated with the store purchases.

#### 3.4 See what factors affect fish purchases

Plot a histogram of fish product purchases
![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/33.png)

Use the previously mentioned linear regression model and evaluate the test data using RMSE.
![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/34.png)

Use feature importance rankings to identify important factors affecting fish purchases.
![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/35.png)

It can be concluded that there are 6 important factors that affect store purchases:

'Total_Mnt', 'MntWines', 'MntMeatProducts', 'MntGoldProds', 'MntSweetProducts', 'MntFruits'

I explore the directionality of these effects using SHAP values:

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/36.png)

1. 'TotalMnt': As the total customer expenditure increases, the amount spent on fish also increases, showing a positive correlation.

2. 'MntWines', 'MntMeatProducts', 'MntGoldProds', 'MntSweetProducts', 'MntFruits':

As the amount spent on wine, meat products, gold products, fruits, or sweets increases, the amount spent on fish decreases.

#### 3.5 Analyze the differences in the acceptance of campaigns in different countries

Create a Choropleth map illustrating the campaigns acceptance levels across different countries.

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/37.png)

The Choropleth map reveals that different countries have varying levels of acceptance for different campaigns. Among them, Mexico shows the highest level of acceptance, particularly evident in campaign 3 and the most recent campaign. Across all campaigns, the most recent campaign has the highest level of activity acceptance.

### 4. Data Visualization
#### 4.1 Campaign acceptance

In this section, I will plot the overall acceptance rate of the campaign and analyze which type of activity is most easily accepted by customers.

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/38.png)

response has the highest customer acceptance.

#### 4.2 Average Characteristics of Customers

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/39.png)

#### 4.3 Most Popular Product

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/40.png)

It can be seen that the most popular products are wines and meat.

#### 4.4 Acceptance by different channels

![](https://github.com/kklsy109/Marketing_Analytics/blob/main/pictures/41.png)

It can be observed that the acceptance level is higher for stores and web pages, while the worst is for advertising campaigns and DealsPurchases.

### 5.Conclusion

Marketing Recommendations:

1.The most successful campaign was the recent 'Response' campaign, with the highest acceptance rate in the Mexican region.

2.The acceptance of advertising campaigns shows a positive correlation with income and a negative correlation with the number of children.

3.The best-selling products are wines and meat.

4.WebPurchases and StorePurchases are preferable channels for purchases.

5.DealsPurchases and CatalogPurchases are less effective channels for purchases.
























