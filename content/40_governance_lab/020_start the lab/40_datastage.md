---
title: "2. Data Integration (ETL) Lab"
chapter: true
weight: 20
draft : false
---

# Data Integration (ETL) Lab

## Learning Objectives:
> #### In this tutorial you will learn:
> 1. How to make a connection between external data source and IBM Cloud Pak for Data
> 2. How to create ETL pipeline using IBM DataStage
> 3. How to create scheduling rule to create data integration pipeline.

## Prerequisites
> 1. IBM Cloud Pak for Data
> 2. IBM DataStage
> 3. External Data Sources (Amazon S3, Amazon Aurora PostgreSQL)
> 4. IBM Watson Knowledge Catalog

## Estimated time
It should take you approximately 15 minutes to complete this lab.

## Lab Steps:

> ### Step 1: Login to IBM Cloud Pak for Data

> 1. Login to IBM Cloud Pak for Data with valid credentials

To perform this lab you need IBM Cloud Pak for Data's credential which include both username and password. If you do not have the credentials then refer LAB-0 to get the one.

![Login](/images/30_governance_lab/login.png)

> ### 2. Create new project

Click on the Navigation Menu and expend Projects and click All Projects. Then click `New Project +` and then select `Analytics project` to create new analytics project

![DV Menu](/images/30_governance_lab/project-1.png)

Click `Create an empty project`
![DV Menu](/images/30_governance_lab/project-3.png)

Specify a name to new project and click `Create`
![DV Menu](/images/30_governance_lab/project-4.png)

Once project is created you will see project homepage.
![DV Menu](/images/30_governance_lab/project-5.png)

> ### 3. Create new connections with external data sources.

> 1. Click `New asset +`

![Create connection](/images/30_governance_lab/create_connection.png)

Click `Connection`

![Create connection](/images/30_governance_lab/create_connection_1.1.png)


> 2. Choose Amazon S3 as connection type.

![Amazon S3](/images/30_governance_lab/create_connection_2.png)

> 3. Specify Amazon S3 connection details (Provided as part of Lab - 0 ) to make connection between Amazon S3 and IBM Cloud Pak for Data.

> 4. Click Test connection to validate the connection. If it is successful click Create to create S3 connection.

![Amazon S3 Test Connection](/images/30_governance_lab/test_connection.png)

![Amazon S3 Test Connection](/images/30_governance_lab/s3_test_connection_success.png)

> 5. Similarly perform same step to create connection for asset type Amazon Redshift, and Amazon RDS for PostgreSQL.

![Create connection](/images/30_governance_lab/create_connection.png)

Select Amazon Redshift

![Data Ingestion](/images/30_governance_lab/redshift_connection_page.png)

Specify the connection details provided as part of Lab - 0  and then click on `Test connection`. If test connection is successful, then click `Create` to create new Redshift connection

![Data Ingestion](/images/30_governance_lab/redshift_connection_1.png)

![Create connection](/images/30_governance_lab/create_connection.png)

Select Amazon RDS for PostgreSQL

![Data Ingestion](/images/30_governance_lab/aurora_connection_page.png)

Specify the connection details provided as part of Lab - 0  and then click on `Test connection`. If test connection is successful, then click `Create` to create new Aurora PostgreSQL DB connection

![Data Ingestion](/images/30_governance_lab/aurora_connection.png)

> 6. Since we have created data source connection, now lets ingest data from connected data source. Click `Add asset+` and then click `Connected data`

![Create connection](/images/30_governance_lab/create_connection.png)

![Data Ingestion](/images/30_governance_lab/create_connection_1.1_gen.png)


Click `Select source`
![Data Ingestion](/images/30_governance_lab/select_data_source.png)

Select Amazon S3 connection and select `apotheca_healthcare_personnel_data.csv` and then click `Select`
![Data Ingestion](/images/30_governance_lab/select_connection_source_s3.png)

Specify a name to data asset
![Data Ingestion](/images/30_governance_lab/select_connection_source_s3_1.png)

> 7. Similarly collect data from redshift data source. Click `Add asset+` and then click `Connected data`

![Create connection](/images/30_governance_lab/create_connection.png)

![Data Ingestion](/images/30_governance_lab/create_connection_1.1_gen.png)

Click `Select source`
![Data Ingestion](/images/30_governance_lab/select_data_source.png)

Select Amazon Redshift connection and select `actavis_pharma_healthcare_personnel_table` and then click `Select`
![Data Ingestion](/images/30_governance_lab/redshift_asset_discovery.png)

![Data Ingestion](/images/30_governance_lab/redshift_asset_discovery_1.png)

> 8. Similarly ingest data from Amazon Aurora PostgreSQL database. Click `Add asset+` and then click `Connected data`

![Create connection](/images/30_governance_lab/create_connection.png)

![Data Ingestion](/images/30_governance_lab/create_connection_1.1_gen.png)

Click `Select source`
![Data Ingestion](/images/30_governance_lab/select_data_source.png)

Select Amazon RDS for PostgreSQL connection and select `mylan_specialty_personnel_data_table` and then click `Select`

![Data Ingestion](/images/30_governance_lab/aurora_select_connection_source.png)

![Data Ingestion](/images/30_governance_lab/aurora_connected_data_asset.png)

Finally after adding all three connections and data assets, you could see all assets in the project.

![Data Ingestion](/images/30_governance_lab/final_data_discovery.png)

> 9. To create integration pipeline, let's click Add assets + then DataStage flow.

![DataStage](/images/30_governance_lab/datastage.png)

> 10. Enter DataStage flow name and click Create to create new DataStage flow.

![DataStage](/images/30_governance_lab/datastage_flow_1.png)

> 11. DataStage Homepage. Here you will see three options. Connectors to ingest or output to data source. Stages to perform ETL operation and Quality.

![DataStage Homepage](/images/30_governance_lab/datastage_4.png)

![DataStage Homepage](/images/30_governance_lab/datastage_5.png)

![DataStage Homepage](/images/30_governance_lab/datastage_6.png)

> 12. Click Connectors to expand and then drag and drop Asset Browsers to datastage canvas.

![DataStage Asset Browser](/images/30_governance_lab/datastage_7.png)

> 13. You need to select data assets to create integration pipeline. Select Data asset and then click all three data assets which ingested in previous step and then click Add.

![DataStage Asset Browser](/images/30_governance_lab/browse_asset.png)

> 14. You should be able to see all three data assets as shown below.

![DataStage Asset Browser](/images/30_governance_lab/browse_asset_1.png)

> 15. Now search funnel in the search box and drag and drop Funnel Stage to the canvas.

![DataStage Asset Browser](/images/30_governance_lab/funnel.png)

> 16. Create links from all data assets to Funnel Stage as shown in below picture.

![DataStage Asset Browser](/images/30_governance_lab/funnel_1.png)

> 17. Double click on all three data assets one by one and then click Output tab and then click Edit column to verify Data type, length and nullability of all columns

![DataStage Asset Browser](/images/30_governance_lab/datastage_asset.png)

![DataStage Asset Browser](/images/30_governance_lab/s3_type.png)

![DataStage Asset Browser](/images/30_governance_lab/redshift_type.png)

![DataStage Asset Browser](/images/30_governance_lab/aurora_type.png)

> 18. Search remove duplicate stage and again drag and drop the stage.

![DataStage Asset Browser](/images/30_governance_lab/remove_duplicate_by_1.png)

> 19. Double click on Remove Duplicate Stage and click `Edit` to specify keys that define duplicates

![DataStage Asset Browser](/images/30_governance_lab/remove_duplicate_by_2.png)

Click `Add key +`
![DataStage Asset Browser](/images/30_governance_lab/remove_duplicate_by_3.png)

Specify `id` as key
![DataStage Asset Browser](/images/30_governance_lab/remove_duplicate_by_4.png)

Verify that `id` is coming as key and then click `Save`
![DataStage Asset Browser](/images/30_governance_lab/remove_duplicate_by_5.png)

> 20. Search sort and drag and drop Sort stage.

![DataStage Asset Browser](/images/30_governance_lab/sort_by_1.png)

Double click on Sort stage and then click `Edit` in Sorting Keys.
![DataStage Asset Browser](/images/30_governance_lab/sort_by_2.png)

Select `id` as sort key and click `Apply` button
![DataStage Asset Browser](/images/30_governance_lab/sort_by_3.png)

Click `Apply and return`
![DataStage Asset Browser](/images/30_governance_lab/sort_by_4.png)

Verify that `id` is coming as Sorting key and then click `Save`
![DataStage Asset Browser](/images/30_governance_lab/sort_by_5.png)

> 21. Search `rds` and then drag and drop `Amazon RDS for PostgreSQL` connector to canvas.

![DataStage Asset Browser](/images/30_governance_lab/datastage_output_1.png)

> 22. Double click on RDS connector to specify data source and specify a unique name to SQL table

![DataStage Asset Browser](/images/30_governance_lab/datastage_output_2.png)

> 23. Compile the datastage pipeline and run if compile succeeded.

![DataStage Asset Browser](/images/30_governance_lab/compile.png)

![DataStage Asset Browser](/images/30_governance_lab/compile_success.png)

![DataStage Asset Browser](/images/30_governance_lab/run_success.png)

> 25. Now we have integrated data available in Amazon RDS for PostgreSQL. Let's ingest the data from the data source

![Create connection](/images/30_governance_lab/create_connection.png)

![Data Ingestion](/images/30_governance_lab/create_connection_1.1_gen.png)


Click `Select source`
![Data Ingestion](/images/30_governance_lab/select_data_source.png)

Search the integrated table and click `Select`
![DataStage Asset Browser](/images/30_governance_lab/integrated_table.png)

![DataStage Asset Browser](/images/30_governance_lab/integrated_table_1.png)

![DataStage Asset Browser](/images/30_governance_lab/integrated_table_2.png)


## Summary

This lab you have learned how to create connection with Amazon S3, RDS, and Redshift and how to collect data from these data sources. Also we learned that how to create ETL pipeline using IBM DataStage.
