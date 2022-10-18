---
title: "3. Upload the SageMaker notebooks into Watson Studio project"
weight: 10
chapter: false
draft: false
---

**The SageMaker notebooks from step # 1 have to be uploaded to Cloud Pak for Data.** You can download the notebook below if you have not done it in step # 1. 

**Download** the notebook {{% button href="/data-pre-processing/Data-pre-processing.ipynb" icon="fas fa-download" icon-position="right" %}}Data-pre-processing.ipynb{{% /button %}} into your local file system. 

We will upload **Data-pre-processing.ipynb** notebook into Watson Studio project. The remaining three notebooks are **optional & can be uploaded offline**. 

Log in to the project in Cloud Pak for Data and click on **Assets**

![](/images/20_trusted_ai_lab/assets.png)

Click on **New asset**

![](/images/20_trusted_ai_lab/new-assets.png)

Click on **Code editors**

![](/images/20_trusted_ai_lab/code-editor.png)

Click on **Jupyter notebook editor**

![](/images/20_trusted_ai_lab/nb-editor.png)

Select **From file** option - choose the default runtime (1vCPU & 2GB RAM) to run the notebook. You can click on **Drag and drop files here or upload** and select the **Data-pre-processing.ipynb** notebook from your local file system. Hit the **Create** button to start the upload process of the notebook. 

![](/images/20_trusted_ai_lab/from-file.png)

Click on **Kernel** and choose **Restart & Run All** option as per the sample image below.

![](/images/20_trusted_ai_lab/run-nb.png)

This is how we can build models in Amazon SageMaker and port them into Cloud Pak for Data and run them in Watson Studio.

**Optional**

Repeat the above steps for uploading the remaining notebooks in this repository.

**Note**:- The home directory has to be changed in the SageMaker Notebooks after uploading them into Watson Studio. **Save the model to home directory** cell will need home directory replaced to **"/home/wsuser/work"** in cell numbers 37 to 41 for **WS-Flanders-Predict.ipynb** notebook and cell numbers 36 to 40 for **WS-Belgium-Predict.ipynb** notebook.
