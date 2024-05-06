# Home_Sales
In this challenge, PySpark is utilised to optimise the ability for the csv dataset of Home Sales to be queried. Three different methods for querying this dataset is used; spark session, cached spark session, and partitioned using parquet. As expected, the partitioned method was the faster and most efficient.
## Inputs
As mentioned the dataset containing home sales was used in this investigation, sourced from Amazon AWS (link to csv file; "https://2u-data-curriculum-team.s3.amazonaws.com/dataviz-classroom/v1.2/22-big-data/home_sales_revised.csv") \
The data provided on home sales include: \
* id
* date
* date house was built
* selling price
* number of bedrooms
* number of bathrooms
* square feet of living area
* square feet of lot area
* number of floors
* if it has a waterfront view
* rating out of 100

## Outputs/ Queries
Once a Spark session and temporary view of the data frame has been created, the following queries were ran:
* average price for a four bedroom house sold per year, rounded to two decimal places: \
![image](https://github.com/BradFisher18/Home_Sales/assets/149662706/723a15b0-1ad4-476b-a338-36041e892cd6)

* average price of a home for each year the home was built, that have 3 bedrooms and 3 bathrooms, rounded to two decimal places: \
![image](https://github.com/BradFisher18/Home_Sales/assets/149662706/0da6ad7f-3c4f-4f6d-90c1-1569d364e3c0)

* average price of a home for each year the home was built, that have 3 bedrooms, 3 bathrooms, with two floors,and are greater than or equal to 2,000 square feet, rounded to two decimal places: \
![image](https://github.com/BradFisher18/Home_Sales/assets/149662706/04bce20f-448e-47f6-be76-52a4d6351efb)

* average price of a home per "view" rating, rounded to two decimal places, having an average home price greater than or equal to $350,000? Order by descending view rating., including run time for this query: \
![image](https://github.com/BradFisher18/Home_Sales/assets/149662706/75fc7434-96ad-47ec-8ac3-398b8b9030e2)
\
To be able to investigate if we can optimise the query run time, a cache of the temporary home sales and a partitioned home sales dataset were compared by running the last query as above. The resulting query times from these methods were: \
Cached: \
![image](https://github.com/BradFisher18/Home_Sales/assets/149662706/2a647b19-b0e7-495a-a237-7d8ea39c8b53)
\
Partitioned: \
![image](https://github.com/BradFisher18/Home_Sales/assets/149662706/b76c0701-de26-44d2-83de-28172eeab562)
\
As expected, the partitioned version of the home sales reduced query run time by a third. This therefore proves that if a larger dataset was used, it would make a significant difference in the efficiency for the user reducing time wasted waiting for the query to run.

## Running
For this program to run, Google Colab is to be used, which requires a Google account to be setup (login/ account creation; https://accounts.google.com/signin ) \
Alternatively, Jupyter Notebook may be utilised, however the import code structure would need to be amended to suit, as well as the Spark program files installed. \
One method to install Jupyter Notebook and otehr imports (except PySpark) is to download Anaconda - link below. To run this code, open the file within Jupyter, ensure that the input files are directed correctly and run! \
Anaconda install: https://docs.anaconda.com/free/anaconda/install/ \
Installation and download for Spark can be found at here: https://spark.apache.org/downloads.html
