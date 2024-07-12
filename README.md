# Extracting raw data from source and preprocessing for analysis and modelling.

## Project Overview

This project focuses on customer segmentation through comprehensive analysis of customer behavior. As a Data Engineer, I was responsible for **data extraction**, **preprocessing**, and combining multiple datasets to create a **unified dataset** for analysis and modelling.

## Data Source

An excel file dataset including the following sheets of data:

`-` Transactions_data: This dataset included the transactions data of the customers across 
all the different states in Australia. Including:

  - transaction_id: Unique identifier for each transaction 
  
  - customer_id: Identifier for the customer involved in the transaction 

  - transaction_date: Date when the transaction occurred 

  -  brand: Brand of the product 

  - list_price: Listed price of the product at the time of the transaction 

  - standard_cost: Standard cost of the product to the compan

`-` NewCustomerList: This dataset included the new customers who visited the automobile 
bike company recently (Initially lacking customer ID).

`-` CustomerDemographic: This dataset included entire details of the Customer 
Demographics such as age, gender, and wealth segment.

`-` CustomerAddress: This dataset included the address of the Customers including state and postal code.

## Tools Used

-**Programming Language**: Python

-**Tools and libraries**

`-` Jupyter Notebook

`-` Anaconda (powered jupyter notebook on local system)

`-` Pandas (for data manipulation and analysis)

`-` NumPy (for numerical computations)

`-` Matplotlib and Seaborn (for data visualization)

-**Excel** (for initial data storage)

## Installation

1. Download Ananconda [here](https://www.anaconda.com/download).

2. Open and run the Jupyter Notebook by entering *jupyter notebook* then click enter.

3. Access the notebook in your browser and execute the extraction and preprocessing scripts.

## Data Processing Workflow

### Data Extraction 

First Import libraries needed for extraction and processing into jupyter notebook

-```import pandas as pd```

-```import seaborn as sns```

-```import matplotlib.pyplot as plt```

-```import datetime as dt```

-```from datetime import datetime```

-```import numpy as np```

 **Importing data from excel into jupyter notebook**

```Data=pd.read_excel("Raw_data.xlsx", sheet_name=None)```

 **Importing transactions sheet from Raw_data excel dataset**
 
```Transactions=Data["Transactions"]```

**Nb: best practice to make copy of data**
```t_copy=Transactions.copy()```

Same syntax applied to import the three remaining sheets.

### Exploratory Data Analysis (EDA) 

- To understand the characteristics and structure of the data extracted 

- To identify its format, schema, and any initial quality issues such as missing values, outliers, or inconsistencies. 

`-` Check information in each column and their characteristics :```t_copy.head(5)``` , ```t_copy.shape```, ```t_copy.info()```

`-` Check for missing data: any data needed for segmentation but was not provided (in collaboration with data science and data analysis team)

`-` Check for missing values: ```t_copy.isnull().sum()```

`-` Check for duplicates: ```t_copy.duplicated().sum()```

`-` Check for Outlier: through visualization ```t_copy.hist(figsize=(20,16))
plt.show()```

### Data Cleaning

`-` Missing Values: Identified and replaced missing values using appropriate imputation techniques to maintain data quality. For example, Column *online_order* had 360 missing values,based on **value_counts**, there was an appropriate distribution of values hence a forward fill method to fill in misssing values, syntax: ```t_copy['online_order'].fillna(t_copy['online_order'].mode()[0],inplace=True)```

`-` String Formatting: Standardized string formats across datasets (e.g., consistent capitalization, unified abbreviations).

### Creating Customer IDs

`-` For the NewCustomer List, I traced the last Customer ID from the Customer Demographics table and generated unique Customer IDs for newly onboarded customers.

### Handling Non-Transactional Customers

 `-`Removed customers from the final dataset who had details but no associated transactions, as they contributed to missing values and did not provide value for segmentation.

### Data Preprocessing

`-` Aggregation: Combined transaction details based on Customer ID to create a summarized **Customer Behavior*** dataset, including metrics like:
 - Average amount spent
 - Total amount spent
 - Most purchased brand
 - Number of transactions

`-` Feature Engineering: 
 - Transactions Table:
   
     - Created an RFM (Recency, Frequency, Monetary) column to quantify customer engagement.
     - Added a Profit column to track the profitability of each transaction.

  - CustomerDemographic Table:
    
      - Created an Age column from the date of birth.
      - Added an Age Group column to categorize customers into age ranges (e.g., 18-25, 26-35).

 `-` Joining Datasets: Merged the Customer Behavior dataset with the other datasets:

   - Linked customer demographic information to understand customer profiles.
   - Integrated address details for geographic analysis.
   - Combined data from the new customer list to include insights on recent onboarding.

`-` Format Standardization: Ensured consistent formatting across all datasets for analysis readiness.

### Final Dataset

The final dataset combines all relevant information, providing a full view of customer behavior and demographics, which was essential for effective segmentation and targeted marketing strategies.

### Conclusion

This project enhances the understanding of customer behavior by integrating various datasets and performing thorough data cleaning and feature engineering. This enables effective segmentation and personalized marketing efforts. 
    





      
   


















![Uploading image.png…]()
