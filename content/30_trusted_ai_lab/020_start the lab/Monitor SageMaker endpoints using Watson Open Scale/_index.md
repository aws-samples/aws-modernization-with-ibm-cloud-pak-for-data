---
title: "6. Monitor SageMaker endpoints using Watson Open Scale"
weight: 10
chapter: false
draft: false
---

**Monitor SageMaker endpoints using Watson Open Scale for Fairness, Quality & Drift detection**

Navigate to the [Watson OpenScale Dashboard](https://cpd-zen.apps.efs-cluster-d01.ibmworkshops.com/aiopenscale/insights?serviceInstanceNamespace=zen&serviceInstanceDisplayName=openscale-defaultinstance) to view the different metrics like **Fairness, Quality, Drift** on the SageMaker endpoint. 

Click on Linear Learner SageMaker model in Open Scale canvas which was imported into Watson Open Scale dashboard programmatically. The Fairness & Quality monitoring has been setup using the Watson Studio **SageMaker-Monitor-OpenScale notebook** from previous step.

![](/images/20_trusted_ai_lab/LL-wos.png)

Click on **Actions** and choose **Configure monitors**.

![](/images/20_trusted_ai_lab/conf-mon.png)

Click on **Drift** under Evaluations tab and upload the Drift model tar.gz file (which was downloaded in previous step) by clicking on the pencil icon next to Drift model - click next and upload the file. You can also set **Drift thresholds** & **Sample size** as per your requirement. **For this workshop, you can update Drift thresholds as 25 for Drop in accuracy & 25 for Drop in data consistency. The minimal sample size should be updated as 10 and Maximum sample size can be left blank.**

![](/images/20_trusted_ai_lab/upload-dd-model.png)

You should see a message per below that configuration is saved.

![](/images/20_trusted_ai_lab/dd-model-saved.png)

Click on the option below to configure the metrics.

![](/images/20_trusted_ai_lab/fair-qual.png)

Set up the parameters for **Fairness** per below. **Click on the Pencil icon and set the Fairness threshold as 80%.** You can leave the rest as is. 

![](/images/20_trusted_ai_lab/fairness-threshold.png)

Set up the parameters for **Quality** per below. **Click on the Pencil icon and set the Area under ROC as 0.8.** You can leave the rest as is. 

![](/images/20_trusted_ai_lab/quality.png)

You can view the Watson Open Scale monitor which has metrics like **Fairness, Quality & Drift** set up for monitoring the model endpoints.

![](/images/20_trusted_ai_lab/wos.png)

We are all set to monitor SageMaker endpoints on Watson Open Scale for **Fairness, Quality & Drift** metrics. 

We can observe that **Fairness** metric is showing Green because the threshold is set for 80% and the model endpoint evaluation score is 100%. **If the evaluation score is greater than the set threshold, then the metric will show Green, else it would be in Red.**

The threshold set for **Area under ROC** metric is 0.8 (80%) and the model endpoint evaluation score is 0.83 (83%) which is why the **Quality** metric is showing Green. 

**Explainability** is not set up because the feature works for Binary classification where as Risk Index prediction is multi-class classification use-case. 

**Drift** metrics has been setup and will be triggered when the endpoint generates predictions on new data.

**We have created predictive models in SageMaker, ported them to Cloud Pak for Data, generated SageMaker endpoints using Watson Studio and set up monitoring services using Watson OpenScale for different metrics like Fairness, Quality & Drift.**
