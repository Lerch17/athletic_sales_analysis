# athletic_sales_analysis
Module 5 Challenge

## 1. Combine and Clean the Data

    First I imported pandas. Then I read the CSV files and displayed their info as data frames. I displayed sales data from 2020 and 2021 seperately, and then checked their data types by using .dtypes. After that I combined the data using .concat setting the axis to rows<axis='rows'> and resetting the index with <ignore_index=True>. After this we checked for any null values by applying .isnull() and .sum() to the dataframe, and I can see that there are no null values. I once again check the data type of the combined data with .dtypes I then converted the "invoice_data" to a datetime data type by using .loc to locate 'Invoice_date'inside of my new combined dataframe and convert all instances to datetime datatypes with .to_datetime. I finish by displaying the new dataframe and confirming that the datatype has infact changed to datetime.
## 2. Determine which Region Sold the Most Products
    
    Here is used .groupby to show the number products sold for region, state, and city. I then used .rename to rename 'units_sold' to "Total_Products_sold".
    Ithen used a .pivot_table to display the same information.
## 3. Determine which Region had the Most Sales

    Using .groupby I showed the total sales for the products sold for each region, state, and city.
    I then renamed "total_sales" column to "Total Sales".
    I then did the same thing using a .Pivot_table, by using 'total_sales' as my value and setting the columns to 'region', 'state', and 'city'. then applying the aggfunc 'sum'. After this i again used .rename to rename the "total_sales" column to "Total Sales".

## 4. Determine which Retailer had the Most Sales

    using .groupby again I found all the same information as well as the sales data on 'retailers. I used .rename to rename the "total_sales" column to "Total Sales"
    I did the same thing again using a .pivot_table.

## 5.  Determine which Retailer Sold the Most Women's Athletic Footwear

    Here I filtered the data to focus on women's athletic footwear sales data. I created a new data frame from my first data frame, but this time I only looked for values where the "product" was Womens Athletic Footwear. After i filtered the dataframe the way I wanted, I once again used .groupby and .pivot_table to find the total number of womens footware units sold for each retailer, region, state, and city.

## 6. Determine the Day with the Most Women's Athletic Footwear Sales

    First I created a pivot table with the 'invoice_date' column is the index, and the "total_sales" as the values. I then renamed the "total_sales" column to "Total Sales". After i ran this .pivot_table i used .resample(D') to pivot the table into daily bins and .sum() to get the total sales for each day. I then used .sort_values by Total Sales to order sales based on their values and used ascending = False to put them in decending order. 

## 7. Determine the Week with the Most Women's Athletic Footwear Sales

    Here i did the same thing as above only using .resample('W') to pivot the table into weekly bins and .sum() to calculate the total sales for weach week. I then sorted them with sort_value by Total Sales againn and put them in descending order <ascending = False>. 