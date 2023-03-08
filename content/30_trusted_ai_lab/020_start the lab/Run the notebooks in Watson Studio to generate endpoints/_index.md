---
title: "4. Run the notebooks in Watson Studio to generate predictions and endpoints"
weight: 10
chapter: false
draft: false

---

{{% notice info %}}

You need credentials & you will get them from the ./printcredentials.sh step from the Infrastructure Provisioning Lab. 

* **S3 Bucket Name**
* **SageMaker Access key & Secret Key**
* **SageMaker role**

{{% /notice %}}

**You can run the SageMaker notebook in Watson Studio to deploy the model & generate SageMaker endpoint.**

> **Step 1**

Download the notebook {{% button href="/sagemaker-model-deploy/RI-SageMaker-Deploy-Wstudio.ipynb" icon="fas fa-download" icon-position="right" %}}RI-SageMaker-Deploy-Wstudio.ipynb{{% /button %}} onto your local file system.

**Update the credentials in cell #s 4 and 5 as shown below.**

![](/images/20_trusted_ai_lab/upd-cred.png)

> **Step 2**

Click on **Kernel** and choose **Restart & Run All** option as per the sample image below. 

![](/images/20_trusted_ai_lab/run-nb.png)

**This notebook built in Watson Studio uses SageMaker inbuilt modules (Linear Learner) to create a multi-class classifier model for prediction Risk Index per region.**

We need to upload the notebook into Cloud Pak for Data environment using the same Watson Studio project as shown in previous step. We will run this notebook in Cloud Pak for Data to build the predictive model. **It will take 3 - 5 minutes for creating the SageMaker endpoint.** Please be patient.

The Watson Studio notebook deploys the predictive model on SageMaker platform and creates an endpoint for real-time scoring. 

> **Step 3**

**You need to login to AWS console, search for SageMaker and open the instance, click on Inference - Endpoints on the left pane and copy the endpoint name as shown below. This endpoint was created by the notebook which was executed in Cloud Pak for Data.**

![](/images/20_trusted_ai_lab/endpoint-name.png)
