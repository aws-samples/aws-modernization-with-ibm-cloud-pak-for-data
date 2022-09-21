---
title: "5. Run the notebooks in Watson Studio to generate predictions and endpoints"
weight: 10
chapter: false
draft: false

---

**You can Run the SageMaker notebooks in Watson Studio to generate predictions and scoring SageMaker endpoints.**

`Deploy SageMaker model from Watson Studio & create endpoints`

Download the notebook {{% button href="/sagemaker-model-deploy/RI-SageMaker-Deploy-Wstudio.ipynb" icon="fas fa-download" icon-position="right" %}}RI-SageMaker-Deploy-Wstudio.ipynb{{% /button %}} onto your local file system.

This notebook built in Watson Studio uses SageMaker inbuilt modules (Linear Learner) to create a multi-class classifier model for prediction risk index per region. The Watson Studio notebook deploys the model in SageMaker platform and creates two endpoints with different methodologies for real-time scoring. You can choose the first or the second endpoint for monitoring using Watson OpenScale. Upload the notebooks into Cloud Pak for Data environment using Watson Studio as shown in previous step.
