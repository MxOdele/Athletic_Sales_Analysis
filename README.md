# Athletic_Sales_Analysis

<div align='center'>
    <img src='https://images.pexels.com/photos/4498610/pexels-photo-4498610.jpeg' height='300' title='A woman preparing to work out in her athletic shoes (image courtesy of Pexels)' alt="An image of a woman's legs, cropeed at the knee, with athletic shoes standing beside two small hand weights, a rolled up yoga mat, and a water bottle that reads 'I woke up like this.'" />

*Althletic Sales Analysis*[^1]

## READ ME
</div>

## Table of Contents

* [Overview](#Overview)
* [Execution](#Execution)

---

## Overview

### *The Assignment*

For our Week 5 Challenge we were tasked with completing the provided Jupyter Notebook `athletic_sales_analysis_starter_code.ipynb` to analyze the information in the provided csv files, `athletic_sales_2020.csv` and `athletic_sales_2021.csv`, by combining the data sets, creating pivot tables, and filtering the results to find the top regions for total sales and the top days and weeks for sales of women's athletic footwear. The steps we were charged with completing were:

1. Combining and Cleaning the Data
    1. Importing the `athletic_sales_2020.csv` and `athletic_sales_2021.csv` files into the `athletic_sales_analysis_starter_code.ipynb` notebook
    2. Checking that the two DataFrames (DFs) have similar data types
    3. Combining the two DFs by rows, using an inner join, and resetting the index
    4. Cleaning the concatenated data by;
        * Checking for any null values
            * *Spoiler: There were none*
        * Confirming each column's data types
        * Converting the `invoice_date` column to a datetime data type
        * Confirming the data type was changed
2. Determining which Region Sold the Most Products
    1. Using either the `groupby` or `pivot_table` functions to create a multi-index DF with `region`, `state`, and `city` columns
        * *Note: I opted to do both*
    2. Renaming the aggregated column to reflect the aggregation of the data in the column
    3. Sorting the results in descending order to show the top five (5) regions, with state and city, by greatest number of products sold
3. Determining which Region had the Most Sales
    1. Using either the `groupby` or `pivot_table` functions to create a multi-index DF with `region`, `state`, and `city` columns
        * *Note: I opted to do both*
    2. Renaming the aggregated column to reflect the aggregation of the data in the column
    3. Sorting the results in descending order to show the top five (5) regions, with state and city, by overall sales
4. Determining which Retailer had the Most Sales
    1. Using either the `groupby` or `pivot_table` functions to create a multi-index DF with `retailer`, `region`, `state`, and `city` columns
        * *Note: I opted to do both*
    2. Renaming the aggregated column to reflect the aggregation of the data in the column
    3. Sorting the results in descending order to show the top five (5) retialers, with region, state, and city, by overall sales
5. Determining which Retailer Sold the Most Women's Athletic Footwear
    1. Filtering the combined DF to create a DF with only women's athletic footwear sales data
    2. Using either the `groupby` or `pivot_table` functions to create a multi-index DF with `retailer`, `region`, `state`, and `city` columns
        * *Note: I opted to do both*
    3. Renaming the aggregated column to reflect the aggregation of the data in the column
    4. Sorting the results in descending order to show the top five (5) retialers, with region, state, and city, by overall sales of women's athletic footwear
6. Determining the Day with the Most Women's Athletic Footwear Sales
    1. Creating a pivot table from the filtered data in step 5 (five) with `invoice_date` as the index and `total_sales` as the `values` parameter
    2. Renaming the aggregated column to reflect the aggregation of the data in the column
    3. Applying the `resample` function to place the data into daily bins and get the total sales for each day
    4. Sorting the resampled DF in decending order to show the top ten (10) days by overall sales of women's athletic footwear
7. Determining the Week with the Most Women's Athletic Footwear Sales
    1. Applying the `resample` function the filtered data in step 5 (five) to place the data into weekly bins and get the total sales for each week
    2. Sorting the resampled DF in decending order to show the top ten (10) weeks by overall sales of women's athletic footwear

### *Written in*

Jupyter Notebook using Python v3.10.13 and Pandas

### *Accessing the notebook*

To access the athletic sales analysis notebook, simply download the `.ipynb` file `athletic_sales_analysis_starter_code.ipynb` and the `Resources` folder in this repository into one directory, then load the `athletic_sales_analysis_starter_code.ipynb` file into Jupyter Notebook through your terminal. 

---

## Execution

### *How to use*

Simply `Run All Cells` to execute the code in every cell of the notebook in sequence. Alternatively, each cell may be `Run` on its own, though it is still recommended to run them in order.

### *Breaking down the cells*

Below is a more in-depth explanation of the various cells coded within the `athletic_sales_analysis_starter_code.ipynb` notbook.

| Cell (in order from top to bottom) | Notes[^2] (on the contained code) |
| ---: | :--- |
| 1 | Importing necessary libraries and dependencies *(Pandas and Path from Pathlib)* |
| 2 | Declaring the paths for the `*.csv` files in the `Resources` folder and reading the files into DFs (`df_2020` and `df_2021`) |
| 3 | Displaying the `df_2020` DF |
| 4 | Displaying the `df_2021` DF |
| 5 | Checking data types for the `df_2020` DF |
| 6 | Checking data types for the `df_2021` DF |
| 7 | Combining the `df_2020` and `df_2021` DFs into the `comb_sales_df` working DF with the `.concat()` on an inner join and resetting the index, then displaying the `comb_sales_df` DF to confirm the rows joined properly |
| 8 | Checking for null values in the `comb_sales_df` DF |
| 9 | Checking the data types for the `comb_sales_df` DF |
| 10 | Converting `invoice_date` to a `datetime` data type[^3] |
| 11 | Confirming `invoice_date` chagnged to `datetime` data type |
| 12 | Declaring `grp_reg_tot_unit` as a multi-index DF with `groupby` function, using `region`, `state`, and `city` as indexes, `sum` as the aggregate on `units_sold`, sorting by descending value, and renaming `units_sold` to `Total_Products_Sold`, and then displaying the top five (5) results |
| 13 | Declaring `pvt_reg_tot_unit` as a multi-index DF with `pivot_table` function, using `region`, `state`, and `city` as indexes, `sum` as the aggregate on `units_sold`, sorting by descending value, and renaming `units_sold` to `Total_Products_Sold`, and then displaying the top five (5) results |
| 14 | Declaring `grp_reg_tot_sale` as a multi-index DF with `groupby` function, using `region`, `state`, and `city` as indexes, `sum` as the aggregate on `total_sales`, sorting by descending value, and renaming `total_sales` to `Total Sales`, and then displaying the top five (5) results |
| 15 | Declaring `pvt_reg_tot_sale` as a multi-index DF with `pivot_table` function, using `region`, `state`, and `city` as indexes, `sum` as the aggregate on `total_sales`, sorting by descending value, and renaming `total_sales` to `Total Sales`, and then displaying the top five (5) results |
| 16 | Declaring `grp_ret_tot_sale` as a multi-index DF with `groupby` function, using `retailer`, `region`, `state`, and `city` as indexes, `sum` as the aggregate on `total_sales`, sorting by descending value, and renaming `total_sales` to `Total Sales`, and then displaying the top five (5) results |
| 17 | Declaring `pvt_ret_tot_sale` as a multi-index DF with `pivot_table` function, using `retailer`, `region`, `state`, and `city` as indexes, `sum` as the aggregate on `total_sales`, sorting by descending value, and renaming `total_sales` to `Total Sales`, and then displaying the top five (5) results |
| 18 | Declaring `sales_woms_ath_fw` as a filtered DF of `comb_sales_df` for data with `Women's Athletic Footwear` in the `product` column and resetting the index |
| 19 | Declaring `grp_woms_ath_fw_unit` as a multi-index DF with `groupby` function on the `sales_woms_ath_fw` DF, using `retailer`, `region`, `state`, and `city` as indexes, `sum` as the aggregate on `units_sold`, sorting by descending value, and renaming `units_sold` to `Womens_Footwear_Units_Sold Sales`, and then displaying the top five (5) results |
| 20 | Declaring `pvt_woms_ath_fw_unit` as a multi-index DF with `pivot_table` function on the `sales_woms_ath_fw` DF, using `retailer`, `region`, `state`, and `city` as indexes, `sum` as the aggregate on `units_sold`, sorting by descending value, and renaming `units_sold` to `units_sold`, and then displaying the top five (5) results |
| 21 | Declaring `pvt_woms_ath_fw_sale` as a multi-index DF with `pivot_table` function on the `sales_woms_ath_fw` DF, using `invoice_date` as index, `sum` as the aggregate on `total_sales`, sorting by descending value, and renaming `total_sales` to `Total Sales`, and then displaying the top five (5) results |
| 22 | Declaring `smpl_d_wafws` with the `resample` funciton on the `pvt_woms_ath_fw_sale` DF, breaking the data into daily bins, using `sum` as the aggregate on `Total Sales`, sorting by descending value, and displaying the top ten (10) results |
| 23 | Declaring `smpl_w_wafws` with the `resample` funciton on the `pvt_woms_ath_fw_sale` DF, breaking the data into weekly bins, using `sum` as the aggregate on `Total Sales`, sorting by descending value, and displaying the top ten (10) results |

[^1]: Image courtesy of free source image site, <a href='https://www.pexels.com/photo/unrecognizable-female-athlete-standing-near-sport-accessories-4498610/' title='Link to Pexels listing for image'>Pexels</a>

[^2]: Markdown cells not annotated

[^3]: Included the `format='mixed'` attribute as other formats and discluding the attribute caused non-fatal errors