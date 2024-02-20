# Airflow-Data-Pipeline-AWS-Snowflake

The project demonstrates using the Astronomer Astro SDK to build an Apache Airflow pipeline that loads data from an Amazon S3 bucket into Snowflake, transforms and merges the data, and cleans up temporary tables.

Workflow:

1. Set up an Airflow environment using the Astro CLI. Configure AWS and Snowflake connections in Airflow

2. Load a CSV file from S3 into a temporary Snowflake table using the Astro load_file() operator

3. Filter the orders in the table where amount is greater than 150 using the Astro transform() decorator and SQL

4. Join the filtered orders with a customers table in Snowflake using transform() and SQL

5. Merge the joined table into an existing Snowflake reporting table using Astro merge(). Handles conflicts

6. Transform the reporting table into a Pandas dataframe using Astro dataframe() to process and print dates

7. Clean up temporary tables using Astro cleanup()

The Astro SDK allows writing Airflow pipelines that interact with data in Snowflake using simple Python and SQL, avoiding a lot of boilerplate code. This project shows loading data, transforming it with SQL, merging tables, and converting data to dataframes for processing.
