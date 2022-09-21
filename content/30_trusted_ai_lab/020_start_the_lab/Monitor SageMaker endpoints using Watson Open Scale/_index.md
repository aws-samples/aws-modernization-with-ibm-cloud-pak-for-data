---
title: "7. Monitor SageMaker endpoints using Watson Open Scale"
weight: 10
chapter: false
draft: false
---


`Monitor SageMaker endpoints using Watson Open Scale for Fairness, Quality & Drift detection`

**Please make sure you have created an instance of Watson OpenScale from IBM Cloud catalog and select internal database using manual setup option. You might be asked to sign in to access Watson OpenScale Dashboard.**

Navigate to the [Watson OpenScale Dashboard](https://aiopenscale.cloud.ibm.com/aiopenscale/insights/357fc90a-5d8f-4a51-8fb5-734aa84b2b86/) to view the different metrics like Fairness, Quality, Drift etc on the SageMaker endpoint. The Fairness & Quality monitoring has been setup using the Watson Studio notebook from step 7.

Click on Linear Learner SageMaker model in Open Scale canvas which was imported into Watson Open Scale programmatically using the notebooks from steps 6 & 7.

![](/images/20_trusted_ai_lab/LL-wos.png)

Click on `Actions` and choose `Configure monitors`.

![](/images/20_trusted_ai_lab/conf-mon.png)

click on `Drift` under Evaluations tab and upload the Drift model tar.gz file (which was downloaded in previous step) by clicking on the pencil icon next to Drift model - click next and upload the file. You can also set `Drift thresholds` & `Sample size` as per your requirement.

![](/images/20_trusted_ai_lab/upload-dd-model.png)

You should see a message per below that configuration is saved.

![](/images/20_trusted_ai_lab/dd-model-saved.png)

Click on the option below to configure the metrics.

![](/images/20_trusted_ai_lab/fair-qual.png)

Set up the parameters for `Fairness` per below.

![](/images/20_trusted_ai_lab/fairness-threshold.png)

Set up the parameters for `Quality` per below.

![](/images/20_trusted_ai_lab/quality.png)

You can view the Watson Open Scale monitor which has metrics like `Fairness, Quality & Drift` set up for monitoring the model endpoints.

![](/images/20_trusted_ai_lab/wos.png)

We are all set to monitor SageMaker endpoints on Watson Open Scale for Fairness, Quality & Drift metrics. We can observe that Fairness metric is showing `Green` because the threshold is set for 80% and the score is 100%. The threshold for `Area under ROC` metric is 0.8 (80%) and the score is 0.83 (83%) which is why the Quality metric is showing `Green`. Explainability is not set up because the feature works for binary classification where as Risk Index prediction is multi-class classification use-case. Drift metrics has been setup and will be triggered when the endpoint generates predictions on new data. 
