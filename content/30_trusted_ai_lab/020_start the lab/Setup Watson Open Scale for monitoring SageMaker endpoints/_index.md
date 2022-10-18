---
title: "5. Setup Watson Open Scale for monitoring SageMaker endpoints"
weight: 10
chapter: false
draft: false

---

**Note :-** You need credentials & you will get them from the ./printcredentials.sh step from the Infrastructure Provisioning Lab. 

* **S3 Bucket Name**
* **SageMaker Access key & Secret Key**
* **SageMaker role**
* **CPD username & password**
* **DB2 Hostname, username & password**

---

**You need to download two notebooks into your system.**

**Download** the first notebook {{% button href="/drift-model/Drift-Detection-Model.ipynb" icon="fas fa-download" icon-position="right" %}}Drift-Detection-Model.ipynb{{% /button %}} into your local file system. 

**Upload Drift detection model notebook into Watson Open Scale canvas.** You can upload the notebook into Watson studio project as shown in step #3. 

**Note :- You need to update the credentials in Cell # 18 & the SageMaker endpoint name (you would have got it in the previous step) in cell # 19 and then run all the cells in the notebook by clicking on Kernel - Restart & Run All**. 

![](/images/20_trusted_ai_lab/cred-endpoint.png)

Run all the cells in the notebook **by clicking on Kernel - choose Restart & Run All** as per the sample image below. 

![](/images/20_trusted_ai_lab/run-nb.png)

Click on **Download Drift detection model** option at the end of the notebook and download the tar.gz file into your local file system. A sample tar.gz file is available [here](/drift-model/drift_detection_model.tar.gz). The downloaded file needs to be uploaded into Watson Open Scale canvas as shown in the **next step**. The model has been built and trained on the Risk Index data to learn and highlight when there's a change in model performance or drift in data.  

**Download** the second notebook {{% button href="/open-scale-model-monitor/SageMaker-Monitor-OpenScale.ipynb" icon="fas fa-download" icon-position="right" %}}SageMaker-Monitor-OpenScale.ipynb{{% /button %}} into your local file system. 

**Upload SageMaker Monitor OpenScale notebook into Watson Open Scale canvas.** You can upload the notebook into Watson studio project as shown in step #3.

**Note :- You need to update the credentials in Cell #s 3, 5 & 10 and run all the cells in the notebook by clicking on Kernel - Restart & Run All**.

![](/images/20_trusted_ai_lab/run-nb.png)

This notebook built in Watson Studio uses Watson Open Scale for setup & monitor SageMaker endpoints. The metrics which will be evaluated are **Fairness, Quality & Drift detection** of SageMaker endpoints as per the thresholds set by the user. This will help to identify whether the SageMaker model requires retraining to eliminate bias in the scoring of the data for generating predictions. 

**Explainability** metric has not been configuered as it applies only for Binary Classification models and Risk Index prediction is multiclass classification usecase.
