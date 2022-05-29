## Hypothesis Testing - Housing Price Data

**Project description:** Making use of various statistical methods to test different hypothesis, such as comparing sales price of houses in certain neighbourhood against the population, comparing sales price of houses built before and after 1960, finding out the relationship between the type of land contour and the sales price of houses, etc. 

### 1. Importing modules

Before we embark on the project, let's import the modules that we will be using. 

<img src="images/Import Modules.png?raw=true"/>

### 2. Reading the CSV file

<img src="images/Reading CSV.png?raw=true"/>

### 3. Review the data and get all column names

We should familiarise ourselves with the data that we are analysing. We can also call the describe and info methods to find out more about the dataset (e.g. min, max, mean, median values and data types).  

<img src="images/Review Data.png?raw=true"/>
<img src="images/Get Column Names.png?raw=true"/>

### 4. Plotting the distribution of sales price

As the focus of our analysis is on the sales price of houses, we can plot its distribution to check for potential skewness in data that we should take note of. 

<img src="images/Plot Distribution of Sale Price.png?raw=true"/>
<img src="images/Data Parameters.png?raw=true"/>

In this case, we see that the data is slightly skewed to the right. As the skewness is not severe, we can assume a normal distribution for sales price and rely on parametric hypothesis tests. If not, we can either consider removing the outlier if we have reasons to believe it is due to data entry error, or use nonparametric hypothesis tests which are robust to outliers. 

### 5. Housing price in specific neighbourhoods (1 sample z-test)

Given that we have the population data (i.e. sales price of all the neighbourhoods), we can compare housing price of specific neighbourhoods with the population mean using 1 sample z-test.  

<img src="images/Neighborhood Data Count.png?raw=true"/>
<img src="images/import z test.png?raw=true"/>
<img src="images/z test 1.png?raw=true"/>
<img src="images/z test 2.png?raw=true"/>

From the above, we can deduce that the housing price in Edwards and OldTown are not the same as the population mean. This also tells us that the neighbourhood that a house is in can affect its price. 

### 6. Housing price in specific neighbourhoods (1 sample t-test)

We can also use 1 sample t-test to compare the housing price of specific neighbourhoods.

<img src="images/1 sample t test.png?raw=true"/>

Similarly, we reject the null hypothesis and deduce that the housing price in Edwards is not the same as the population mean. Using a for loop, we can apply the t-test to all neighbourhoods.

<img src="images/Looping 1 sample t test for all neighbourhoods.png?raw=true"/>

### 7. Cumulative Distribution Function 

Using stats.norm.cdf, we can find out how many % of houses in a specific neighbourhood we can afford with $X. 

<img src="images/cdf probability.png?raw=true"/>

### 8. Comparing housing price in different neighbourhoods (independent samples t-test)

Let's compare the house price in Edwards vs. SawyerW using the independent samples t-test.

<img src="images/Independent Samples t test.png?raw=true"/>

From the above, as the p value is much lower than 0.05, we can reject the null hypothesis and conclude that the average house prices in Edwards and SawyerW are not similar.  

### 9. Comparing price of houses built before/after 1960 (independent samples t-test)

We can also use the independent samples t-test to compare the price of houses built before and after a specific year (e.g. 1960).

<img src="images/plot count of house built in each year.png?raw=true"/>
<img src="images/Independent Samples t test (price of house before and after 1960).png?raw=true"/>

As the p value is much lower than 0.05, we can reject the null hypothesis and conclude that the price of houses built before and after 1960 are not similar.









