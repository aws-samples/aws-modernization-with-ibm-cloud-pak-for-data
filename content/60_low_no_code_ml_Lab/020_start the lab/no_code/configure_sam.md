---
title: "4.2. Configure SAM"
weight: 65
chapter: true
draft: false
---

# Configure SAM

{{% notice info %}}
In this section, you will configure a Serverless Application Module (SAM) with credentials to access the Watson Machine Learning model deployed in previous section. This SAM will be used as a backend server on AWS that will talk to IBM Cloud Pak for Data Watson Machine Learning service to get predictions from the deployed model.
{{% /notice %}}

## Configure Serverless Application Module (SAM)

1. In AWS Console, Navigate to **Services -> Compute -> Lambda**.

1. Select the Lambda function with the description **Invoke WML model endpoint**.

1. You will see the Lambda function overview as shown.
![lambda-function-overview](/images/50_low_no_code_ml_Lab/lab4-ext-lambda-overview.png?classes=shadow)

1. You can take a look at the code source below function overview. There are two main functions in the server:
  - `GetToken()`: This function makes an API call to IBM Cloud Pak for Data-Auth Validation and generates a bearer token that will be used invoke Watson Machine Learning Model deployed on Cloud Pak for Data.
  ![get-token-function](/images/50_low_no_code_ml_Lab/lab4-ext-get-token-fn.png?classes=shadow)
  - `InvokeModel()`: This function makes an API call to IBM Cloud Pak for Data-Watson Machine Learning with scoring payload, and gets the model prediction and probability result.
  ![invoke-model-function](/images/50_low_no_code_ml_Lab/lab4-ext-invoke-model-fn.png?classes=shadow)

5. To generate the Token and Invoke the model, you need to provide Cloud Pak for Data credentials to the Lambda function.

1. Select the **Configuration** tab below function overview.
![lambda-function-config](/images/50_low_no_code_ml_Lab/lab4-ext-lambda-config-tab.png?classes=shadow)

1. You will see a left panel with different options, select **Environment variables**. You will see 3 environment variables listed.

1. Click on **Edit** and enter the following details:
  - **CPD_PASSWORD:** Password used to login to Cloud pak for Data
  - **CPD_USERNAME:** Username used to login to Cloud pak for Data
  - **CPD_WML_MODEL_ENDPOINT:** Cloud pak for Data Watson Machine Learning model deployed endpoint url copied from previous step.

{{% notice tip %}}
As part of Infra Provisioning Lab, you will have created CP4D users. Enter the same user credentials for **CPD_USERNAME** and **CPD_PASSWORD**.
{{% /notice %}}

9. Click on **Save** to update the environment variables.
![edit-env-variables](/images/50_low_no_code_ml_Lab/lab4-ext-edit-env.gif?classes=shadow)

1. At this point you have successfully configured the Serverless Application Module(SAM) backend.