# Extracting raw data from source and preprocessing for analysis and modelling.

### Project Overview

This project focuses on data extraction and preprocessing tasks to prepare raw data for analysis and modelling. 
It includes techniques for importing data from excel to jupyter notebook, cleaning, transforming, and integrating datasets to ensure data quality and usability.

### Data Source

An excel file dataset including the following sheets of data:

`-` Transactions_data: This dataset included the transactions data of the customers across 
all the different states in Australia.

`-` NewCustomerList: This dataset included the new customers who visited the automobile 
bike company recently.

`-` CustomerDemographic: This dataset included entire details of the Customer 
Demographics.

`-` CustomerAddress: This dataset included the address of the Customers.

### Tools Used

-**Programming Language**: Python

-**Tools and libraries**

`-` Jupyter Notebook

`-` Anaconda (powered jupyter notebook on local system)

`-` Pandas (for data manipulation and analysis)

`-` NumPy (for numerical computations)

`-` Matplotlib and Seaborn (for data visualization)

-**Excel** (for initial data storage)

### Installation

1. Download Ananconda [here](https://www.anaconda.com/download).

2. Open and run the Jupyter Notebook by entering *jupyter notebook* then click enter.

3. Access the notebook in your browser and execute the extraction and preprocessing scripts.

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

To understand the characteristics and structure of the data extracted and
to identify its format, schema, and any initial quality issues such as missing values, outliers, or inconsistencies. 

`-` Check information in each column and their characteristics :```t_copy.head(5)``` , ```t_copy.shape```, ```t_copy.info()```

`-` Check for missing data: any data needed for segmentation but was not provided (in collaboration with data science and data analysis team)

`-` Check for missing values: ```t_copy.isnull().sum()```

`-` Check for duplicates: ```t_copy.duplicated().sum()```

`-` Check for Outlier: through visualization ```t_copy.hist(figsize=(20,16))
plt.show()```

### Data Preprocessing

`-` Data Cleaning: misising values in each column handled based on 


















![Uploading image.png…]()
