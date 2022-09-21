---
title: "Reference Architecture"
weight: 15
chapter: true
draft: false
pre: "<b>A. </b>"
---

# Data Access & Governance Reference Architecture.

![architecture](/images/30_governance_lab/lab2-ref-architecture.png?classes=shadow)

## Flow

1. Create external connection between external data sources (eg. Amazon S3, and Amazon Aurora PostgreSQL) and IBM Cloud Pak for Data.
2. Use IBM Data Virtualization to query data from multiple data sources without creating data replica.
3. Use IBM DataStage to create ETL pipeline
4. Use IBM Data Refinery Flow to clean, and filter the data.
5. Use IBM Watson Knowledge Studio to profile and govern the data.
6. Supply the data to AI based predictive system such as Amazon SageMaker or Jupyter Notebook to create machine learning models.
