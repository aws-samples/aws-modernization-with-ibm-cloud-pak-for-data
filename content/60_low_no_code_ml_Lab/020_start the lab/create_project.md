---
title: "1. Setup a project in Cloud Pak for Data"
weight: 15
chapter: true
draft: false
---

# Setup a project in Cloud Pak for Data

<link rel=stylesheet href=https://cdn.jsdelivr.net/npm/hamburger-menu@0.3/dist/hamburger-menu.min.css>

<script src=https://cdn.jsdelivr.net/npm/jquery@3.6/dist/jquery.min.js></script>
<script src=https://cdn.jsdelivr.net/npm/hamburger-menu@0.3/dist/hamburger-menu.min.js></script>

{{% notice info %}}
In this step, you will learn to create a project and setup a connection to Amazon S3 bucket in your IBM Cloud Pak for Data. This is essential because all the dataset resides in Amazon S3 Bucket.

{{% /notice %}}

## Create project in Cloud Pak for Data

- Before you get started, download the {{% button href="/project/cpd4.5/IBM-AWS-Immersion-Day-Lab-4.zip" icon="fas fa-download" icon-position="right" %}}IBM-AWS-Immersion-Day-Lab-4.zip{{% /button %}} project.

- Create a project in IBM Cloud Pak for Data. Click on the <b>&#9776;</b> menu, and select **All Projects**.

  ![cpd-projects](/images/50_low_no_code_ml_Lab/cpd-all-projects.png?classes=shadow)

- Click on **New Project**.
  - Select project type as **Analytics project**.
  - Click on **Create a project from file**.
  - Upload the **[IBM-AWS-Immersion-Day-Lab-4.zip](/project/cpd4.5/IBM-AWS-Immersion-Day-Lab-4.zip)** file.
  - Enter a project name and click on **Create**.

- Once the project is created click on **View Project**. You should see the overview of the project as shown below.

  ![cpd-dashboard](/images/50_low_no_code_ml_Lab/cpd-project.png?classes=shadow)

- Click on the **Assets** tab and you will see **Data** and **Notebooks**.

## Create a Connection to S3

- Click on **New Asset**, under **Data access tools** select **Connection**.

- Select Connection type as **Amazon S3**.
  - Enter name of the connection as `AWS-S3`.
  - Enter the following credentials to connect to your S3 bucket.
    - Bucket
    - Endpoint URL
    - Region
    - Credential setting: **personal**
    - Authentication method: **basic credentials**
    - Access Key
    - Secret Key
  - Click on **Test connection** and you will see connection successful message if you have entered the correct credentials.
  - Click on **Create**.

  ![successful-connection](/images/50_low_no_code_ml_Lab/connection-successful.png?classes=shadow)

> Note: Name the connection variable as `AWS-S3` as it is used in code section of the Jupyter Notebooks.

- Once the connection is created, you will see the connection in Assets tab under **Data assets**. With this connection you can access all the datasets present in your S3 bucket from your Cloud Pak for Data project.