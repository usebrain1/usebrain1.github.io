## Learning Points from Pre-Processing of City Payroll Data 

**Description:** There were a few discrepancies in the city payroll data which need to be cleaned up before we go into hypothesis testing. I have documented some of these below.

### 1. Use of .info() method to review data count and data type

Call the .info() method to see if there are any missing data for any particular columns and if the variables are of the desired data type. 

<img src="images/city payroll_city payroll info.png?raw=true"/>

We can see that there are quite a number of missing values in the Payroll Department column as compared to the rest. Fields like Projected Annual Salary and Base Pay are also classified as object data type instead of float. 

### 2. Filter out rows with null values and rename columns

To ensure that every column has similar number of non-null rows to facilitate our analysis, we can call the pd.notnull() method to filter out rows with null values.

<img src="images/city payroll_filter null.png?raw=true"/>
<img src="images/city payroll_city payroll info (after filtering null).png?raw=true"/>

Now, every column has 231463 non-null rows.

### 3. Removing $ symbol and convert data to float

We will also need to remove the '$' symbol and convert the salary data to float before we proceed to conduct the hypothesis tests.
To remove the '$' symbol, we can call the string replace() method to replace '$' with '' (i.e. blank).
To convert data to float, we can call the pandas DataFrame.astype() method.

<img src="images/city payroll_remove dollar sign symbol.png?raw=true"/>
<img src="images/city payroll_convert datatype to float.png?raw=true"/>
<img src="images/city payroll_after converting datatype to float.png?raw=true"/>

Now, we can proceed to perform the hypothesis tests.
