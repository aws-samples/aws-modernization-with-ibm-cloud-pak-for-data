---
title: "6. Monitor SageMaker endpoints using Watson Open Scale"
weight: 10
chapter: false
draft: false
---

**Monitor SageMaker endpoints using Watson Open Scale for Fairness, Quality & Drift detection**

{{% notice info %}}

**We need to get Watson OpenScale URL from the Cloud Pak for Data console**. Login to Cloud Pak for Data console, click on **Instances**.

![](/images/20_trusted_ai_lab/wos-cpd.png)

Look for **OpenScale** instance, do a Right Click on the instance name and click on **Copy Link Address** and paste the URL in a new tab in the browser. 

![](/images/20_trusted_ai_lab/wos-url.png)

**Login to Watson OpenScale instance (with the URL above) by using the Cloud Pak for Data credentials generated in the Infra Provisioning Lab.**

{{% /notice %}}

> **Step 1**

Navigate to the Watson OpenScale Dashboard to view the different metrics like **Fairness, Quality, Drift** on the SageMaker endpoint. 

> **Step 2**

Click on Linear Learner SageMaker model in Open Scale canvas which was imported into Watson Open Scale dashboard programmatically. The Fairness & Quality monitoring has been setup using the Watson Studio **SageMaker-Monitor-OpenScale notebook** from previous step.

![](/images/20_trusted_ai_lab/LL-wos.png)

> **Step 3**

Click on **Actions** and choose **Configure monitors**.

![](/images/20_trusted_ai_lab/conf-mon.png)

> **Step 4**

Click on **Drift** under Evaluations tab and upload the Drift model tar.gz file (which was downloaded in previous step) by clicking on the pencil icon next to Drift model - click next and upload the file. You can also set **Drift thresholds** & **Sample size** as per your requirement. **For this workshop, you can update Drift thresholds as 25 for Drop in accuracy & 25 for Drop in data consistency. The minimal sample size should be updated as 10 and Maximum sample size can be left blank.**

![](/images/20_trusted_ai_lab/upload-dd-model.png)

You should see a message per below that configuration is saved.

![](/images/20_trusted_ai_lab/dd-model-saved.png)

> **Step 5**

Click on the option below to configure the metrics.

![](/images/20_trusted_ai_lab/fair-qual.png)

> **Step 6**

Set up the parameters for **Fairness** per below. **Click on the Pencil icon and set the Fairness threshold as 80%.** You can leave the rest as is. 

![](/images/20_trusted_ai_lab/fairness-threshold.png)

> **Step 7**

Set up the parameters for **Quality** per below. **Click on the Pencil icon and set the Area under ROC as 0.8.** You can leave the rest as is. 

![](/images/20_trusted_ai_lab/quality.png)

> **Step 8**

Click on **Dashboard** to view the Watson Open Scale monitor which has metrics like **Fairness, Quality & Drift** set up for monitoring the model endpoints.

![](/images/20_trusted_ai_lab/wos.png)

> **Step 9**

Click on the second option in the left pane per below to view **Explainability** metric.

![](/images/20_trusted_ai_lab/explain-1.png)

Select the **Deployed model** from the dropdown and hit **Explain** on any transaction of your choice. In the below screenshot, first transaction is selected for Explainability.

![](/images/20_trusted_ai_lab/explain-2.png)

In this screen, under **Explain** tab, you will see the Feature Importance analyzed with **LIME** technique. We will understand the significant variable influencing the outcome. 

![](/images/20_trusted_ai_lab/explain-3.png)

You can click on **Inspect** to change the values on real-time and analyze the new predictions. This will help to identify the feature importance for different set of input values. 

![](/images/20_trusted_ai_lab/explain-4.png)

We are all set to monitor SageMaker endpoints on Watson Open Scale for **Fairness, Quality, Explainability & Drift** metrics. 

We can observe that **Fairness** metric is showing Green because the threshold is set for 80% and the model endpoint evaluation score is 100%. **If the evaluation score is greater than the set threshold, then the metric will show Green, else it would be in Red.**

The threshold set for **Area under ROC** metric is 0.8 (80%) and the model endpoint evaluation score is 0.83 (83%) which is why the **Quality** metric is showing Green. 

**Explainability** metrics will identify the feature importance for the predicted outcomes which will be beneficial for analyzing the feature values influencing the outcome.

**Drift** metrics was setup manually in the previous step and will be triggered when the endpoint generates predictions on new data.

**We have created predictive models in SageMaker, ported them to Cloud Pak for Data, generated SageMaker endpoint using Watson Studio and set up monitoring services for the SageMaker endpoint using Watson OpenScale for different metrics like Fairness, Quality, Explainability & Drift.**
