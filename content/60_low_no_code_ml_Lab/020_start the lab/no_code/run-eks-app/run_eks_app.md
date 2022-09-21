---
title: "4.3. RI-Prediction App"
weight: 70
chapter: true
draft: false
---

# RI-Prediction App

{{% notice info %}}
In this section, you will explore the Risk Index Prediction Application running on Amazon Elastic Kubernetes Service (EKS). The intent of this section is to simulate how existing applications running on AWS can invoke the IBM Watson Machine Learnig model with customizations.
{{% /notice %}}

## Architecture Overview of the Risk Index Prediction Application

The Risk Index Prediction application is built using the following client-server architecture:

- Client: ReactJS
- Server: Nginx

Access the {{% button href="http://risk-index-prediction-app.ibmworkshops.com/" target="_blank" icon="fas fa-external-link-alt" icon-position="right" %}}Risk Index Prediction Application{{% /button %}}

The app will look something as shown below.
![ri-app](/images/50_low_no_code_ml_Lab/lab4-ext-ri-app.png?classes=shadow)

1. You need to enter the Amazon API Gateway Endpoint URL for the Lambda function that you configured in previous step.

{{% notice tip %}}
This URL is the **SamEndpointUrl** provided in Infra Provisioning Lab.
{{% /notice %}}

2. You can upload a dataset with n rows of data and get the risk index prediction along with probability. Download this sample {{% button href="/files/test-data.csv" icon="fas fa-download" icon-position="right" %}}test-data.csv{{% /button %}} file and upload it in the application.
3. You can also see the visual representation of this activity with architecture diagram to understand the flow better.

You can then analyse the risk index predictions and probability along with the scoring data in a table format.
![application-execution](/images/50_low_no_code_ml_Lab/lab4-ext-app.gif?classes=shadow)
