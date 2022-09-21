---
title: "6. Setup Watson Open Scale for monitoring SageMaker endpoints"
weight: 10
chapter: false
draft: false
---


This step requires IBM Cloud API Key. You can generate one by referring to this [link.](https://www.ibm.com/docs/en/app-connect/containers_cd?topic=servers-creating-cloud-api-key)

This step requires Cloud Object Storage credentials. You can generate one by referring to this [link.](https://cloud.ibm.com/login) and follow the below steps.

![](/images/20_trusted_ai_lab/sel-cos.png)

Follow the steps to create a Cloud Object Storage instance `Lite` plan and then create bucket per below.

![](/images/20_trusted_ai_lab/crt-bkt.png)

![](/images/20_trusted_ai_lab/crt-cred.png)

![](/images/20_trusted_ai_lab/new-cred.png)

![](/images/20_trusted_ai_lab/copy-cred.png)

We should copy the bucket name, API key and service id crn to be updated in the `SageMaker-Monitor-OpenScale` notebook.

`Setup the monitoring of SageMaker endpoint on Watson Open Scale`

Download the notebook {{% button href="/open-scale-model-monitor/SageMaker-Monitor-OpenScale.ipynb" icon="fas fa-download" icon-position="right" %}}SageMaker-Monitor-OpenScale.ipynb{{% /button %}} into your local file system.

This notebook built in Watson Studio uses Watson Open Scale for setup & monitor SageMaker endpoints. The metrics which will be evaluated are Fairness, Quality & Drift detection of SageMaker endpoints as per the thresholds set by the user. This will help to identify whether the SageMaker model requires retraining & eliminate bias in the scoring of the data to generate predictions.

`Upload Drift detection model file into Watson Open Scale canvas`

Download the notebook {{% button href="/drift-model/Drift-Detection-Model.ipynb" icon="fas fa-download" icon-position="right" %}}Drift-Detection-Model.ipynb{{% /button %}} into your local file system. You can upload the notebook into Watson studio as shown in step #5. You need to update the credentials in Cell number 18 and the name of the SageMaker endpoint in cell number 19 and then run the notebook. Capture the SageMaker endpoint from the AWS SageMaker console under `Inference` section and click on `Endpoints`.

![](/images/20_trusted_ai_lab/cred-endpoint.png)

![](/images/20_trusted_ai_lab/endpoint-name.png)

Run all the cells in the notebook (`by clicking on Kernel - choose Restart & Run All`) & click on `Download Drift detection model` option at the end of the notebook and download the tar.gz file into your local file system. A sample tar.gz file is available [here](/drift-model/drift_detection_model.tar.gz). The downloaded file needs to be uploaded into Watson Open Scale canvas as shown in the next step. The model has been built and trained on the Risk Index data to learn and highlight when there's a change in model performance.  
