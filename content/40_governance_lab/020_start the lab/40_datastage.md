---
title: "2. Data Integration (ETL) Lab"
chapter: true
weight: 20
draft : false
---

# Data Integration (ETL) Lab

## Learning Objectives:
> #### In this tutorial you will learn:
> 1. How to make a connection between external data source and IBM Cloud Pak for Data.
> 2. How to create ETL pipeline using IBM DataStage.
> 3. How to create scheduling rule to create data integration pipeline.

## Prerequisites
> 1. IBM Cloud Pak for Data
> 2. IBM DataStage
> 3. External Data Sources (Amazon S3, Amazon Aurora PostgreSQL)
> 4. IBM Watson Knowledge Catalog

## Estimated time
It should take you approximately 15 minutes to complete this lab.

## Lab Steps:

> #### Step 1: Login to IBM Cloud Pak for Data

To perform this lab you need IBM Cloud Pak for Data's credential which include both username and password. If you do not have the credentials then refer **Infra Provisioning Lab** to get the one.

![Login](/images/30_governance_lab/login.png)

> #### Step 2: Create new project

Click on the Navigation Menu and expend Projects and click All Projects. Then click **New Project +** and then select **Analytics project** to create new analytics project

![DV Menu](/images/30_governance_lab/project-1.png)

Click **Create an empty project**
![DV Menu](/images/30_governance_lab/project-3.png)

Specify a name to new project and click **Create**
![DV Menu](/images/30_governance_lab/project-4.png)

Once project is created you will see project homepage.
![DV Menu](/images/30_governance_lab/project-5.png)

> #### Step 3: Create new connections with external data sources.

1. Click on **Assets** tab and then click **New asset +**

![Create connection](/images/30_governance_lab/create_connection.png)

Scroll down and click **Connection**

![Create connection](/images/30_governance_lab/create_connection_1.1.png)


2. Choose **Amazon S3** as connection type.

![Amazon S3](/images/30_governance_lab/create_connection_2.png)

3. Specify Amazon S3 connection details such as name, bucket name, endpoint, region, and credential details(Provided as part of _Infra Provisioning Lab_ ) to make connection between Amazon S3 and IBM Cloud Pak for Data.

4. Click Test connection to validate the connection. If it is successful click **Create** to create S3 connection.

![Amazon S3 Test Connection](/images/30_governance_lab/test_connection.png)

![Amazon S3 Test Connection](/images/30_governance_lab/s3_test_connection_success.png)

5. Similarly perform same step to create connection for asset type **Amazon Redshift**, and **Amazon RDS for PostgreSQL**.

![Create connection](/images/30_governance_lab/create_connection.png)

Again from the project page, click **New asset +** and then click Connections. Select **Amazon Redshift** connector from available connectors

![Data Ingestion](/images/30_governance_lab/redshift_connection_page.png)

Specify the connection details provided as part of _Infra Provisioning Lab_  and then click on **Test connection**. If test connection is successful, then click **Create** to create new Redshift connection

![Data Ingestion](/images/30_governance_lab/redshift_connection_1.png)

In the project home page, click **New asset+** to create Amazon RDS connection.

![Create connection](/images/30_governance_lab/create_connection.png)

Select Amazon RDS for PostgreSQL

![Data Ingestion](/images/30_governance_lab/aurora_connection_page.png)

Specify the connection details provided as part of _Infra Provisioning Lab_  and then click on **Test connection**. If test connection is successful, then click **Create** to create new Aurora PostgreSQL DB connection

![Data Ingestion](/images/30_governance_lab/aurora_connection.png)

6. Since we have created data source connection, now lets ingest data from connected data source. Click **Add asset+** and then click **Connected data**

![Create connection](/images/30_governance_lab/create_connection.png)

![Data Ingestion](/images/30_governance_lab/create_connection_1.1_gen.png)


Click **Select source**
![Data Ingestion](/images/30_governance_lab/select_data_source.png)

Select Amazon S3 connection and select **apotheca_healthcare_personnel_data.csv** and then click **Select**
![Data Ingestion](/images/30_governance_lab/select_connection_source_s3.png)

Specify a name to data asset
![Data Ingestion](/images/30_governance_lab/select_connection_source_s3_1.png)

7. Similarly collect data from redshift data source. Click **Add asset+** and then click **Connected data**

![Create connection](/images/30_governance_lab/create_connection.png)

![Data Ingestion](/images/30_governance_lab/create_connection_1.1_gen.png)

Click **Select source**
![Data Ingestion](/images/30_governance_lab/select_data_source.png)

Select Amazon Redshift connection and select **actavis_pharma_healthcare_personnel_table** and then click **Select**
![Data Ingestion](/images/30_governance_lab/redshift_asset_discovery.png)

![Data Ingestion](/images/30_governance_lab/redshift_asset_discovery_1.png)

8. Similarly ingest data from Amazon Aurora PostgreSQL database. Click **Add asset+** and then click **Connected data**

![Create connection](/images/30_governance_lab/create_connection.png)

![Data Ingestion](/images/30_governance_lab/create_connection_1.1_gen.png)

Click **Select source**
![Data Ingestion](/images/30_governance_lab/select_data_source.png)

Select Amazon RDS for PostgreSQL connection and select **mylan_specialty_personnel_data_table** and then click **Select**

![Data Ingestion](/images/30_governance_lab/aurora_select_connection_source.png)

![Data Ingestion](/images/30_governance_lab/aurora_connected_data_asset.png)

Finally after adding all three connections and data assets, you could see all assets in the project.

![Data Ingestion](/images/30_governance_lab/final_data_discovery.png)

> #### Step 4: Create DataStage pipeline

1. To create integration pipeline, let's click Add assets + then DataStage flow.

![DataStage](/images/30_governance_lab/datastage.png)



2. **Download** the DataStage pipeline zip file here {{% button href="/datastage/Datastage_Integration_Pipeline.zip" icon="fas fa-download" icon-position="right" %}}Datastage_Integration_Pipeline.zip{{% /button %}}.

3. Click **ZIP file import** tab and click _Drag and drop file here or upload_ to upload the zip file
![](/images/30_governance_lab/datastage_new_flow_1.png)

4. After uploading file click **Import**
![](/images/30_governance_lab/datastage_new_flow_2.png)

5. You will see the screen with Import successful with error. ignore the errors for the moment and close the dialog/popup.
![](/images/30_governance_lab/datastage_new_flow_3.png)

6. Click on the datastage asset icon 
![](/images/30_governance_lab/datastage_new_flow_4.png)

7. You will see a datastage pipeline where data is ingested from 3 different sources and there are different stages (to perform ETL operation on incoming data) such as **Funnel** to merge/integrate data, **Remove_Duplicates** stage to filter out duplicates from integrated data, **Sort** stage to sort the data and finally we are storing the data in Amazon RDS database.
![](/images/30_governance_lab/datastage_new_flow_5.png)

8. Now lets link the data assets in this pipeline.

9. Double click on **actavis_pharma_healthcare_personnel_table_1**
![](/images/30_governance_lab/datastage_new_flow_6.png)

10. Ignore the error and Close the error popup. This is because we have not yet link the data assets with the datastage pipeline.
![](/images/30_governance_lab/datastage_new_flow_7.png)

11. Expand **Properties** option
![](/images/30_governance_lab/datastage_new_flow_8.png)

12. Click **Connection**. here you will see connection which you have created earlier in this lab. Select the connection and click **Save**
![](/images/30_governance_lab/datastage_new_flow_9.png)

13. Repeat the same steps for **mylan_specialty_personnel_data_table_1** connection.

14. Now click on **apotheca_healthcare_personnel_data_1** and choose the S3 connection under Connection option similar what we did in the last steps. **But** here you also need to specify the S3 Bucket name which you should receive as the output of infra provisioning lab. 
![](/images/30_governance_lab/datastage_new_flow_10.png)

15. Click **Save**

16. Double Click **Amazon_RDS_for_PostgreSQL_1**
![DataStage](/images/30_governance_lab/datastage_new_flow_10_1.png)

17. Update Connection as shown below. **Don't** click save.
![DataStage](/images/30_governance_lab/datastage_new_flow_11.png)

18. Specify the name to output table name. eg **Datastage_Output_Table_v1** and then click **Save**
![](/images/30_governance_lab/datastage_new_flow_12.png)

19. Click **Compile** to validate if everything is file. Within a few seconds you should get **Compile successful.** message.
![](/images/30_governance_lab/datastage_new_flow_13.png)

20. Click **Run** to run the pipeline. After a few couple of seconds you should see Run successful message.
![](/images/30_governance_lab/datastage_new_flow_14.png)

> #### Step 4: Ingest the integrated data into the project
1. Now we have integrated data available in Amazon RDS for PostgreSQL. Let's ingest the data from the data source

![Create connection](/images/30_governance_lab/create_connection.png)

![Data Ingestion](/images/30_governance_lab/create_connection_1.1_gen.png)


2. Click **Select source**
![Data Ingestion](/images/30_governance_lab/select_data_source.png)

3. Search the integrated table and click **Select**
{{% notice note %}}
The file name should be same what you have specified as the output. eg. **Datastage_Output_Table_v1**
{{% /notice %}}
![DataStage Asset Browser](/images/30_governance_lab/integrated_table.png)

4. Specify the name of the asset
![DataStage Asset Browser](/images/30_governance_lab/integrated_table_1.png)

5. Verify the data asset is there in project. This asset will be used later in the next lab.
![DataStage Asset Browser](/images/30_governance_lab/integrated_table_2.png)


## Summary

This lab you have learned how to create connection with Amazon S3, RDS, and Redshift and how to collect data from these data sources. Also we learned that how to create ETL pipeline using IBM DataStage.
