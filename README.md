# Power BI Assignment 1
## Data Transformation and Data Modeling
### E-Commerce Sales Analysis:

This assignment will help you explore e-commerce sales data analysis using Power BI. 
Below are the files you will be working with (click on each to download): 
★ List of Orders.csv 
★ Order Details.csv 
★ Sales target.csv 
In this exercise, you will leverage Power BI's capabilities to import, transform, model, and 
analyze the provided data.

#### Data Transformation: 

● Restrict the "List of Orders" table to only the first 500 rows. 
  <br>files open in PowerBI and Transform  file to Powerquery.
  Home -->Keeprows -->Keep range of rows-->specify first row and number of rows to 500-->OK.
 
● Ensure the “Order Date” column in the “List of Orders” table is set to data type 'Date'. 
  <br> Select Order Date column-->Using Locale-->Change Datatype to Date and choose model to display-->OK.

● Change the data type of “Amount” and “Target” columns to ‘Fixed Decimal Number’. 
     <br>Select Target Column-->Change Datatype-->Fixed Decimal.
     <br>Select Amount Column-->Change Datatype-->Fixed Decimal.

● Format the "CustomerName" column into proper case, ensuring consistent 
  capitalization for each word. 
<br>Select CustomerName Column-->Transform-->ABC Format-->Capitalize each word.

● Merge the "State" and "City" columns to create a new column named "Location" in 
the format ‘City, State’.
<br>Select City,State Columns-->Merge Columns-->Select Seperator as comma-->Add new column name as Location-->OK.

● Create a new custom column named "Profit Margin" as the percentage of "Profit" 
divided by "Amount".
<br>TableTools-->NewColumn-->Profit_Margin = Order_details[Profit]/Order_details[Amount]  .

● Add a new conditional column named "Profit Status" based on the values in the 
"Profit" column. The conditions are as follows: if the profit is less than 0, the label 
should be "Loss"; if the profit equals 0, the label should be "Break-Even"; and if the 
profit is greater than 0, the label should be "Profit". 

<br>TableTools-->NewColumn-->Profit_Status = SWITCH(TRUE(),Order_details[Profit]<0,"Loss",Order_details[Profit]=0,"Break-Even","Profit")  .

### Merging Data (Joins): 
● Merge the "List of Orders" and "Order Details" tables into a new single table named 
"Orders Data" based on the "Order ID" relationship.
<br>Merge Queries-->Select List of Orders-->Select Order ID-->Select Order Details as Second table-->Select LeftOuter(All from First,matching from Second)-->OK.
  Change Table mode and Select Columns to show-->OK .

### Handling Missing Data & Duplicate Data: 
● Identify missing values in the data and determine a strategy to address them. 
<br>
● Check for duplicate rows and define a strategy to handle duplicates.
<br>Create Duplicate of Order Data-->Home-->GroupBy--> Select OrderID-->New Column: Count , Operation: Count Rows-->OK.The Table diaplays OrderID and their Count.If Count=1 represent unique Id. If Count equal to more than one represent table have duplicates.Select Home-->RemoveRows-->Remove Duplicates.In Table Duplicate Raws Removed.

### Sorting and Filtering Data: 
● In the ‘Orders Data’ table, utilize sorting and filtering techniques on columns like 
Order Date, State or Category to analyze data based on specific criteria: 
◆ Sort the orders by Order Date in descending order to analyze recent trends. 
◆ Filter the orders to focus only on a specific state (e.g., Tamil Nadu) for 
regional analysis.
