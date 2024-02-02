## Home Sales Data Analysis with Apache Spark

### Overview
This repository contains Apache Spark code for analyzing home sales data. The analysis provides insights into home sales trends based on different criteria such as bedrooms, bathrooms, floors, square footage, and view ratings. Caching and partitioning strategies are employed to optimize query performance, demonstrating the scalability and efficiency of Apache Spark for big data analytics.

#### Code Explanation

##### 1. Data Loading and Exploration
- The data is loaded from an AWS S3 bucket into a Spark DataFrame.
- Sample data is displayed, and summary statistics are generated to understand the dataset.

##### 2. Querying Data
- Queries are performed to answer specific questions about home prices based on different criteria:
  - Average price for a four-bedroom house sold in each year.
  - Average price of homes for each year they were built with three bedrooms and three bathrooms.
  - Average price of homes for each year built with three bedrooms, three bathrooms, two floors, and at least 2,000 square feet.
  - Average price of homes with a price greater than or equal to $350,000, grouped by view rating.

##### 3. Caching and Optimization
- The dataset is cached to improve performance for subsequent queries.
- The runtime for cached and uncached queries is compared to evaluate performance improvements.

##### 4. Parquet Data Partitioning
- The data is partitioned by the "date_built" field and saved in Parquet format.

##### 5. Querying Partitioned Data
- Queries are executed on the partitioned Parquet data to analyze average prices based on view ratings.
- The runtime for querying partitioned data is compared to uncached and cached versions.


#### Comparison of Cached and Uncached Queries

- **Original Data**:
  - **Cached Query Runtime**: Approximately 1.11 seconds.
  - **Uncached Query Runtime**: Approximately 1.31 seconds.

- **Partitioned Parquet Data**:
  - **Cached Query Runtime**: Approximately 0.94 seconds.

The cached query with the original data had a runtime of approximately 1.11 seconds, while the uncached query took approximately 1.31 seconds. With the partitioned parquet data, the cached queries had a runtime of approximately 0.94 seconds. The cached query demonstrated improved performance due to data caching, reducing the runtime compared to the uncached query for the original dataset.


#### Instructions for Google Colab

##### 1. Open Google Colab:

   Go to [Google Colab](https://colab.research.google.com/) and sign in with your Google account.

##### 2. Open In Colab:
   
   Click the "Open in Colab" button at the top of the code file to open it directly in Google Colab.

##### 3. Run the Code:
   Run each cell sequentially by clicking the play button or pressing Shift+Enter.
##### 4. Review Results:
   Review the outputs and analysis results in the Colab cells to gain insights into home sales trends.




