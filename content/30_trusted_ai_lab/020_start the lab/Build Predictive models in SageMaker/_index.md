---
title: "1. Build Predictive models in SageMaker"
weight: 10
chapter: false
draft: false
---

> #### Note:
> Data (COVID19BE_HOSP.csv & COVID19BE_CASES_AGESEX.csv) required for this lab has been uploaded to Amazon S3 bucket as the part of infrastructure automation. **Update the BUCKET_REGION as us-east-2**.

Kindly keep the credentials from CPD, S3, SageMaker, DB2 handy for getting started with Trusted AI.

**You would need the below for this Lab** :- You will get these details in the **./printcredentials.sh** step from the Infrastructure Provisioning Lab.

* **S3 Bucket Name**
* **SageMaker Access key & Secret Key**
* **SageMaker role**
* **CPD username & password**
* **DB2 Hostname, username & password**

**Download** the notebook {{% button href="/data-pre-processing/Data-pre-processing.ipynb" icon="fas fa-download" icon-position="right" %}}Data-pre-processing.ipynb{{% /button %}} into your local file system.

**Please make sure to update the Region, Access Key & Secret Key in the Notebook wherever specified before running the notebook.**

**We have created multiple SageMaker Notebooks for this lab to simulate the Data Science experience.** You can start by uploading **Data-pre-processing.ipynb** notebook and try the remaining three notebooks offline using the same process.

**Create a SageMaker Notebook instance**

Login to the SageMaker console and click on Notebook instances under Notebook in the navigation pane.

![](/images/20_trusted_ai_lab/sm-login.png)

Click on create notebook instance, give it at name like **Lab1**, select the Notebook instance type as **ml.t2.medium**, Platform Identifier as **Amazon Linux 2, Jupyter Lab 1** & IAM role as shown below. It will take a couple of minutes for the instance to be created. Be patient!

![](/images/20_trusted_ai_lab/crt-nb-sm.png)

After the instance is created, click on open Jupyter. Click on **Upload** on the top right side to upload notebooks. 

Select the Kernel as **conda_python3** when prompted and choose **Set Kernel** option. 

**Note**:-You can upload all the notebooks in one go by clicking on UPLOAD option, select the notebooks and run them in SageMaker. After the notebooks are uploaded, it will reflect per below.

![](/images/20_trusted_ai_lab/opn-nb-sm.png)

**After uploading the notebook/s, click on the notebook hyperlink to open it, update the AWS credentials, click on Kernel and choose Restart & Run All option.** 

![](/images/20_trusted_ai_lab/opn-nb-sm.png)

![](/images/20_trusted_ai_lab/run-nb.png)

**You should see something like this after successfully running the Notebooks.**

![](/images/20_trusted_ai_lab/nb-run.png)

**Let's download the SageMaker Notebook/s to be ported to Cloud Pak for Data - Select/Open the notebook - click on File - Download as - Notebook(.ipynb) into your local file system.** >  

![](/images/20_trusted_ai_lab/dw-nb-sm.png)

**Optional**

**Repeat these steps for the other notebooks offline.**

**Download** the remaining three notebooks {{% button href="/notebooks/Notebooks.zip" icon="fas fa-download" icon-position="right" %}}Notebooks.zip{{% /button %}} into your local file system and unzip the file. Follow the process above to upload them into SageMaker, run the notebooks and download the notebooks into your local system which can be ported to Cloud Pak for Data.
