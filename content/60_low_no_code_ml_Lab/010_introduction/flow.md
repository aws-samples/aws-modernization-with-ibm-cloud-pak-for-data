---
title: "Reference Architecture"
weight: 15
chapter: true
draft: false
pre: "<b>A. </b>"
---

# Reference Architecture

![architecture](/images/50_low_no_code_ml_Lab/aws-architecture-lab-4.png)

## Flow

1. Pre-processed datasets from Lab 1 are loaded into an Amazon S3 bucket.
2. The datasets from the S3 bucket are read in IBM Cloud Pak for Data Watson Studio Jupyter Notebooks.
3. Different models are built and evaluated in Jupyter Notebooks and the final prediction data is stored back into Amazon S3 bucket.
4. The prediction data produced by the Jupyter Notebook models stored in S3 bucket is read by IBM IBM Cloud Pak for Data Cognos Dashboard Embedded to visualize the data in the form of interactive dashboard.
5. The datasets from the Amazon S3 bucket is copied into IBM Cloud Pak for Data Watson Studio Project and loaded into AutoAI.
6. Different models are built and compared in AutoAI with no code.
7. The best performing model is selected and deployed in IBM Cloud Pak for Data Watson Machine Learning and an endpoint URL is exposed for online scoring
8. An AWS Serverless Application Module (SAM) is configured with the Watson Machine Learning model endpoint and credentials so that SAM can invoke the model with scoring payload.
9. Risk Index Prediction application running on Amazon Elastic Kubernetes Service (EKS) is configured with the AWS Serverless Application Module (SAM) and the application reads CSV files with n rows of scoring data and sends it to SAM and gets back the predictions and probability from Watson Machine Learning and displays it a table.
