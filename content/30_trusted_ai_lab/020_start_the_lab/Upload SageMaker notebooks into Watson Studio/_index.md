---
title: "4. Upload the SageMaker notebooks into Watson Studio project"
weight: 10
chapter: false
draft: false
---

**The SageMaker notebooks have to be uploaded to Cloud Pak for Data.**

Log in to the project in Cloud Pak for Data and click on `Assets` 

![](/images/20_trusted_ai_lab/assets.png)

Click on `New asset`

![](/images/20_trusted_ai_lab/new-assets.png)

Click on `Code editors`

![](/images/20_trusted_ai_lab/code-editor.png)

Click on `Jupyter notebook editor`

![](/images/20_trusted_ai_lab/nb-editor.png)

Select `From file` option - choose the default runtime (1vCPU & 2GB RAM) to run the notebook. 

![](/images/20_trusted_ai_lab/from-file.png)

Click on `Kernel` and choose `Restart & Run All` option.

![](/images/20_trusted_ai_lab/run-nb.png)

**`Repeat the above steps for uploading all the notebooks in this repository.`** This is how we can build models in AWS SageMaker and port them into Cloud Pak for Data and run them in Watson Studio.

**Note:- The home directory has to be changed in the SageMaker Notebooks after uploading them into Watson Studio. `Save the model to home directory` cell will need home directory replaced to `/home/wsuser/work` in cell numbers 37 to 41 for `WS-Flanders-Predict.ipynb` notebook and cell numbers 36 to 40 for `WS-Belgium-Predict.ipynb` notebook.**
