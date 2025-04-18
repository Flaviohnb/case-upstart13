# Case Upstart 13 - Data Engineer - Flávio Nascimento

Interview Case Study

## About

The solution uses technologies (Docker, Python, Spark). The architecture is based on [**Medallion Architecture**](https://www.databricks.com/glossary/medallion-architecture), from a 3-layer data store consisting of (raw, cleaned, enriched). The raw data is stored in the *raw* layer, prepared and processed in *cleaned*, with the business rules and calculations in *enriched*.

## Result

1. Data Loading: 

- Raw data is saved in the **/datalake/raw** directory by notebooks files in **/scripts** with the prefix name "sourceToRaw_". The ".csv" files saved in **/datalake/raw** have the prefix "raw_" in their names.

2. Data Review and Storage:

- Review data is saved in the **/datalake/cleaned** directory by notebooks files in **/scripts** with the prefix name "rawToCleaned_". The ".parquet" files saved in **/datalake/cleaned** have the prefix "store_" in their names.

3. Product Master Transformations:

- The publish_product table is saved in the **/datalake/enriched/** directory in parquet format, by notebook in **/scripts** named "cleanedToEnriched_publishProduct".

4. Sales Order Transformations:

- The publish_orders table is saved in the **/datalake/enriched/** directory in parquet format, by notebook in **/scripts** named "cleanedToEnriched_publishOrders".

5. Analysis Questions:

- The answers to these questions were developed in a notebook called "analysis_questions" in **/scripts**.

## Run locally

1. Install docker;
2. Unzip the project;
3. With a prompt of your choice, run the command below in the same directory as the file "docker-compose.yml":
    - `docker-compose up -d`
4. If everything is OK, you can open Jupyter Notebook in your browser here:
    - `localhost:8888`