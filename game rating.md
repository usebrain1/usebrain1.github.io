## Region vs. Game Rating - Chi-Square Test 

**Project description:** The objective of this project is to determine if there are any relationship between the regions where games were made vs. the ratings that such games received from Singapore's Infocomm Media Development Authority (IMDA).

### 1. Data

First, let's have a look at our dataset. 

<img src="images/game_rating_dataset.png?raw=true"/>

### 2. Rows containing multiple regions

Given that the region column is one of the factors that we want to analyse, we should call the unique() method to understand what are the unique values under the region column. 

<img src="images/unique_region_names.png?raw=true"/>

Note that some games were produced in multiple regions (e.g. EURO, US). For such cases, we want to split them into 2 rows, each row containing only 1 region. This is to facilitate our subsequent hypothesis testing where we do not want categories such as (EURO, US).

### 3. Split regions by ',' and create a list of regions for each row

To do that, we call the string split() method to create a list of regions. Example, 'EURO, US' will become [EURO, US]. 

<img src="images/split_by_comma_create_region_list.png?raw=true"/>

### 4. Explode the rows

Next, we can call the explode() method to split rows with 2 regions into 2 separate rows. Now, we will no longer see a combination of regions (e.g. EURO, US) as a unique value under the region column.

<img src="images/explode_new_unique_regions.png?raw=true"/>

### 5. Check unique values for rating column

Let's also check the unique values for the rating column to ensure that the data is okay before we proceed.

<img src="images/unique_rating.png?raw=true"/>

### 6. Chi-square test

Finally, we can proceed with the chi-square test to determine if there is a relationship between the regions where games were produced vs. the ratings that such games received. 

<img src="images/region_rating_chi square test.png?raw=true"/>

Given that the p value is higher than 0.05, we fail to reject the null hypothesis. We cannot conclude that there is a relationship between the region and game rating.
