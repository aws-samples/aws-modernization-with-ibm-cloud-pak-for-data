---
title: "1. Data Virtualization Lab"
chapter: true
weight: 10
draft : false
---

# Data Virtualization Lab

## Learning Objectives:
> #### In this tutorial you will learn:
> 1. How to make a connection between external data sources & IBM CP4D connectors.
> 2. How to query multiple data sources wihout creating data replicas using IBM Data Virtualization service.

## Learning Outcome:
At the end of the workshop you will learn how to connects multiple data sources across locations by creating one virtual data view. 

For this workshop, you have Covid-19 regional data stored in **Amazon S3** and **Amazon Aurora PostgreSQL** data sources. In this workshop you will use **IBM Data Virtualization  Service** to create virtual data view.

The proposed solution will solves data silos challenges faced by enterprises which force them to copy the data into centralized repository for analytics.

## Prerequisites:
> 1. IBM Cloud Pak for Data
> 2. Data Virtualization on IBM Cloud Pak for Data
> 3. External Data Sources (Amazon S3, Amazon Aurora PostgreSQL)
> 4. IBM Watson Knowledge Catalog

## Estimated time:
It should take you approximately 10-15 minutes to complete this lab.

## Lab Steps:

>#### Step 1: Login to IBM Cloud Pak for Data with valid credentials

To perform this lab you need IBM Cloud Pak for Data's user credentials (eg. userxxxx) which you have created earlier. Credentials include both username and password. If you do not have the credentials then refer **Infra Provisioning Lab** exercise to get the credentials.

![Login](/images/30_governance_lab/login.png)

>#### Step 2: Create connection with AWS data sources using IBM CP4D connectors

In this lab, you will create connection with **Amazon S3**, and **Amazon RDS** data sources. Follow the below steps to create connection with those data sources:

1. Click Navigation Menu -> Expand 'Data' and then click 'Data Virtualization'

![DV Menu](/images/30_governance_lab/dv_1.png)

2. In the Data Virtualization Page, Click Add connection + New Connection.

![DV Homepage](/images/30_governance_lab/dv_2_new.png)

![Amazon Aurora Connection](/images/30_governance_lab/dv_4.png)

3. Select 'Amazon RDS for PostgreSQL' connection type and then click on **Select**.

![Amazon Aurora Connection](/images/30_governance_lab/DV_Create_Aurora_Connection_Option.png)

You can also specify a _connection name_ and other details as shown in below image then click **Create** to create **Amazon RDS** connection.

![Amazon Aurora Connection Details](/images/30_governance_lab/dv_5_v2.png)
![Amazon Aurora Connection Details](/images/30_governance_lab/dv_5.2_v2.png)

4. Click skip

![Skip](/images/30_governance_lab/skip.png)

5. Similarly add **Amazon S3** datasource by selecting connection type _Amazon S3_ and fill connection details provided using _Infra Provisioning Lab_. Similar to previous connection, You will have to specify the _connection name_ and other required information such as _Bucket_, _Endpoint URL_, _Region_, _Credentials (Shared, Basic)_. 
![](/images/30_governance_lab/dv_s3_1.png)
![](/images/30_governance_lab/dv_s3_1.png)

6. Once you create both data sources connection successfully, you should see both _Amazon S3_ and _Amazon RDS PostgreSQL_ connection listed on the Data sources page as shown below.

![Connection List](/images/30_governance_lab/connection_list_new.png)

>#### Step 3: Create virtual tables

_Congratulations!_

In the previous step you have successfully created connection between external data sources and **Data Virtualization** service. Now you can select tables and file from the connection and create virtualized tables or objects. Once tables are virtualized you can create a VIEW by joining two virtual tables.

1. Open the Data Virtualization menu and click on **Virtualization** to expand and then click **Virtualize** as shown below.

![Virtualize Menu](/images/30_governance_lab/virtualize_menu.png)

2. Click on connection (eg **Amazon RDS for PostgreSQL**) and then you might see several tables under public schema.

{{% notice note %}}
If there are multiple connections listed, choose only one which you have created in previous step.
{{% /notice %}}

![Create Virtual Table](/images/30_governance_lab/create_virtual_table_1.png)

Select the tables (**ts_wallonia_region_table** and **ts_flanders_region_table**) one by one and then click Add to cart. Once after adding both the tables to the cart, click View cart.

![Create Virtual Table](/images/30_governance_lab/create_virtual_table_2.png)

3. As shown in this screen, Select the **Virtualize Data** option and provide a **unique name** to table (in the image below names are ts_wallonia_region_table and ts_flanders_region_table). 

{{% notice note %}}
You might need tables name in the next step. so, note it down for future reference.
{{% /notice %}}

![Create Virtual Table Options](/images/30_governance_lab/virtualize_1.1.png)

Now click on three dots and then click **Edit columns** option (eg **ts_flanders_region_table**) to verify name, type and length of the columns matches with image below and click **Apply**.

![Create Virtual Table Options](/images/30_governance_lab/virtualize_1.2.png)

{{% notice warning %}}
Match the column name, type and length with the above image. Otherwise you may get error while creating View.
{{% /notice %}}

Repeat the same step for another table (here **ts_wallonia_region_table**).

Once after making the changes click Apply and then click **Virtualize** in **Review cart and virtualize table** page.

4. Click **Continue** to create Virtual tables.

![Create Virtual Table Confirmation](/images/30_governance_lab/create_virtualize_table_confirmation.png)

Click **Virtualize more data** option

![Create Virtual Table Confirmation 1](/images/30_governance_lab/create_virtualize_table_confirmation_1.png)

5. In the last step we Virtualized the tables coming from Amazon RDS connection, now let's use csv file coming from Amazon S3 connection and Virtualize it. Click **Files** tab in the **Virtualize** page as shown below and then click **Endpoint**

![Virtualize Menu](/images/30_governance_lab/virtualize_file.png)

6. Navigate to **regional** folder inside parent bucket and select **ts-Brussels-grouped-21-04.csv** as shown in below image and then click **Add to cart** then **View Cart**

![Virtualize Menu](/images/30_governance_lab/virtualize_file_1.1.png)

7. In the **Review cart and virtualize page** specify unique name to the table and note it down for future reference, and then click **Modify columns** button to review columns metadata.

![Virtualize Menu](/images/30_governance_lab/virtualize_file_3.1.png)

8. **Edit the column name, type, and length** as shown in below image and then click **Apply**

{{% notice warning %}}
Match the column name, type and length with the below image. Otherwise you may get error while creating View.
{{% /notice %}}

![Virtualize Menu](/images/30_governance_lab/virtualize_file_3.2.png)

9. In the **Review cart and virtualize page** check **Virtualized data** option then click **Virtualize** button.

10. Click **Continue** to create Virtual tables.

![Create Virtual Table Confirmation](/images/30_governance_lab/create_virtualize_table_confirmation.png)

11. Click **Go to virtualized data**

![Virtualize Menu](/images/30_governance_lab/virtualize_file_3.4.png)

>#### Step 4: Create VIEW by joining two virtual tables/objects
Till now we have created connections with external data sources and from external data sources we picked tables and files to Virtualize them. Now we will use those Virtualize tables/objects and join them to create a VIEW. This VIEW will give us capability to query multiple data sources without creating data replicas.

You can follow below steps to create VIEW:

1. Click **Data Virtualization** menu and expand **Virtualization** and then click **Virtualized Data** option.

![Virtualized Data Menu](/images/30_governance_lab/view_menu.png)

2. Select the virtual tables which you have created in the previous step. (eg here **ts_wallonia_region_table** and **ts_flanders_region_table**) and click Join.

{{% notice note %}}
You may see multiple tables, choose only those two that you have created.
{{% /notice %}}

![Select Tables](/images/30_governance_lab/Join_View_1.1.png)

3. Join two tables by specify join key and then click **Preview** to preview joined table.

![Select Tables](/images/30_governance_lab/Join_View_1.2.png)

4. Close preview page, click **Next** on **Join virtual objects** page

![Select Tables](/images/30_governance_lab/Join_View_1.3.png)

5. Edit the column names as shown in below image. **Make sure you have all column names in smallcase**

![Edit Column](/images/30_governance_lab/Join_View_1.4.png)

6. Once after ensuring all details, provide unique view name (eg. flanders_wallonia_joined_view), select **Virtualized data** checkbox and click **Create view**.

![Select Tables](/images/30_governance_lab/Join_View_1.5.png)

Click go to virtualized data

![Select Tables](/images/30_governance_lab/Join_View_1.6.png)

7. Click 'Virutalized Data' and Select joined view you created in previous step (eg. **flanders_wallonia_joined_view**) and **ts_Brussels-grouped-21-04_csv** table to create view.

![](/images/30_governance_lab/Join_View_1.7.png)

8. Specify **date** as join Key and click **Preview**

![](/images/30_governance_lab/Join_View_1.8.png)

![](/images/30_governance_lab/Join_View_1.9.png)

9. Edit the column names as shown below

![](/images/30_governance_lab/Join_View_1.10.png)

10. Specify the view name (eg. **brussels_wallonia_flanders_joined_view**) and click **Create view**

![](/images/30_governance_lab/Join_View_1.11.png)

By following all the steps you have created a single joined view from different data source. Now let's go to the **Catalog** to view the data.

11. Click navigation bar and expand **Catalogs** and click All Catalogs and select **default catalog** to see the view we created in last step.

![Select Tables](/images/30_governance_lab/catalog_menu.png)

12. In the **Default Catalog** page you will see the joined view (brussels_wallonia_flanders_joined_view) which you have created in the last step. If you noticed view started from **ADMIN.** which is the username. In your case, it might start with **<USER_NAME>.brussels_wallonia_flanders_joined_view**.

Click on the view for more details.

![](/images/30_governance_lab/joined_view_1.png)

13. Click **Assets** tab and provide your Cloud Pak for Data user credentials(**userxxxx**).

![](/images/30_governance_lab/joined_view_2.png)
![](/images/30_governance_lab/joined_view_3.png)

14. After successfully validating credentials, you will be able to see the integrated data.

![](/images/30_governance_lab/joined_view_4.png)

15. Click on the **Profile** tab to get statistics of data inside view.

![](/images/30_governance_lab/joined_view_5.png)

## Summary

This lab you have learned how to use Data Virtualization on IBM Cloud Pak for Data to virtualize data and create merged VIEW to query multiple data sources without moving or copying the data. You have also learned how view can be exported to catalog and how IBM Watson Knowledge Catalog can generate statistics of the data inside view.
