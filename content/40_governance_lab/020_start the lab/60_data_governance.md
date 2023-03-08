---
title: "4. Data Governance Lab"
weight: 40
chapter: true
draft : false
---

# Data Governance Lab

Data governance and security are bigger challenges when data spans an on-premises and cloud infrastructure. In this lab you will learn how to protect sensitive data using data masking rules.

## Learning Objectives:
> #### In this tutorial you will learn:
> 1. How to Create Rules/Policies for masking/obfuscating Email Address and Last name
> 2. How to attach rules to the data asset

## Prerequisites
> 1. IBM Cloud Pak for Data
> 4. IBM Watson Knowledge Catalog

## Estimated time
It should take you approximately 15 minutes to complete this lab.

## Lab Steps:

>#### Step 1: Create Rules for Data Masking and Obfuscating

We have healthcare personnel data which we integrated and cleansed in the last (ETL) lab. Healthcare personnel data contains **sensitive PII** information. In this lab we will create Rules and Policies to mask and obfuscate **Email address** and **last name**.

1. Click navigation menu then expand Governance and then click Rules.

![Data Ingestion](/images/30_governance_lab/governance_1.png)

2. Click Add rule -> New rule

![Data Ingestion](/images/30_governance_lab/rules.png)
![Data Ingestion](/images/30_governance_lab/governance_3.png)

3. Add rule for Email Address masking. Select **Email Address** data class to mask the data. When you profile your assets (in the catalog), a data class will be inferred from the contents where possible.

![Data Ingestion](/images/30_governance_lab/rules_1.png)
![Data Ingestion](/images/30_governance_lab/governance_9.png)

4. Create rule for last name obfuscation

![Data Ingestion](/images/30_governance_lab/rules.png)
![Data Ingestion](/images/30_governance_lab/governance_3.png)
![Data Ingestion](/images/30_governance_lab/governance_10.png)
![Data Ingestion](/images/30_governance_lab/governance_11.png)

5. We have created two rules for Email address and lastname. Let's create **Category** PII_CATEGORY. The fundamental abstraction in Watson Knowledge Catalog is the Category.

![Data Ingestion](/images/30_governance_lab/governance_13.png)
![Data Ingestion](/images/30_governance_lab/governance_14.png)
![Data Ingestion](/images/30_governance_lab/governance_15.png)
![Data Ingestion](/images/30_governance_lab/governance_16.png)

6. Again from the Main Menu, select Business Term under Governance. Use **Business Term** to define business concepts in a standard way that makes your data consistent and easy to understand across the enterprise. Follow the below steps to create Business Term and publish it. 

![Data Ingestion](/images/30_governance_lab/governance_24.png)
![Data Ingestion](/images/30_governance_lab/governance_23.png)
![Data Ingestion](/images/30_governance_lab/governance_25.png)
![Data Ingestion](/images/30_governance_lab/governance_26.png)

7. Create Policy and attach PII_CATEGORY to the policy.

![Data Ingestion](/images/30_governance_lab/governance_17.png)
![Data Ingestion](/images/30_governance_lab/governance_18.png)

8. Add both rules in Data Protection rules of Policy and Publish Policy.

![Data Ingestion](/images/30_governance_lab/governance_22.png)


9. Go back to catalog and open reshaped asset and then click on `plus (+)` icon in the `Governance artifacts` ->`Business terms` as showm in below image.


![Data Ingestion](/images/30_governance_lab/catalog_governance.png)
![Data Ingestion](/images/30_governance_lab/catalog_governance_1.png)
![Data Ingestion](/images/30_governance_lab/catalog_governance_2.png)

10. Go back to the catalog which you have created and click **Access control** tab and click **Add collaborators +**

![](/images/30_governance_lab/add_user_to_catalog_1.png)

11. Add datascientist user which might have received during this lab as collaborator with **Viewer** role.

![](/images/30_governance_lab/add_user_to_catalog_2.png)

With the above all steps you have successfully created data masking and obfuscating rules to protect sensitive data. also with the last step you have provided access of governed data to data scientist. Now let's follow below steps to see whether data scientist receive masked data or not.

12. Login using datascientist or developer credential to see masked Email Address and obfuscated last name.

![Data Ingestion](/images/30_governance_lab/governance_49.png)

## Summary

This lab you have learned how to create data protection rules and apply it to protect sensitive information using IBM Watson Knowledge Catalog.
