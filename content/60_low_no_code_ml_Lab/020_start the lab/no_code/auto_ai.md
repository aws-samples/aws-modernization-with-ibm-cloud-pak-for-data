---
title: "4.1. Build and Deploy model with AutoAI"
weight: 60
chapter: true
draft: false
---

# Build and Deploy model with AutoAI

{{% notice info %}}
In this section, you will build and train high-quality predictive models quickly with no-code and simplify AI lifecycle management using Watson Studio's AutoAI. AutoAI automates tasks for data scientists, tasks such as feature engineering and selection, choosing the type of machine learning algorithm; building an analytical model based on the algorithm; hyperparameter optimization, training the model on tested data sets and running the model to generate scores and findings.

{{% /notice %}}

## Create and Run an AutoAI Project

1. Navigate to the project, click on **Add to project** option on top right and select **AutoAI experiment** as asset type.

1. Create an AutoAI experiment by giving it a name.
![alt-text](/images/50_low_no_code_ml_Lab/autoai-add.png?classes=shadow)

1. Add the data file, click on **Select from project** and select the `RI-data-ML.csv` file from the project's data assets.
![alt-text](/images/50_low_no_code_ml_Lab/auto-ai-2.png?classes=shadow)

1. Click on **No** for creating a time series forecast. We are building a multi class classifier. Select `Risk_Index` as the option to predict and hit **Run experiment**.
![alt-text](/images/50_low_no_code_ml_Lab/auto-ai-3.png?classes=shadow)

1. It will take a couple of minutes to complete the experiment. You will see Experiment completed on the right side of the canvas.
![alt-text](/images/50_low_no_code_ml_Lab/gen-pipe.png?classes=shadow)

1. Review the eight pipelines generated per below.
![alt-text](/images/50_low_no_code_ml_Lab/rev-pipelines.png?classes=shadow)

1. Click on first pipeline (Rank 1) and choose **Save as** option on the top right side.
![alt-text](/images/50_low_no_code_ml_Lab/save-pipeline.png?classes=shadow)

1. Click on **create**.
![alt-text](/images/50_low_no_code_ml_Lab/save-as-model.png?classes=shadow)

1. You should see the message Model saved successfully per below. Click on **View in project** option.
![alt-text](/images/50_low_no_code_ml_Lab/model-saved.png?classes=shadow)

1. Click on **Promote to deployment space**.
![alt-text](/images/50_low_no_code_ml_Lab/promote-to-dep.png?classes=shadow)

1. Under Target space, create a new deployment space.
![alt-text](/images/50_low_no_code_ml_Lab/new-dep.png?classes=shadow)

1. Give a name to the deployment and hit create.
![alt-text](/images/50_low_no_code_ml_Lab/new-dep-2.png?classes=shadow)

1. The deployment space gets created in a minute.
![alt-text](/images/50_low_no_code_ml_Lab/dep-space.png?classes=shadow)

1. Select the option **Go to the model in the space after promoting it** and click on **Promote**.
![alt-text](/images/50_low_no_code_ml_Lab/prom-dep.png?classes=shadow)

1. You will be redirected to the deployment space.
![alt-text](/images/50_low_no_code_ml_Lab/deployment-space.png?classes=shadow)

1. Click on **New deployment**. Select Deployment type as **Online**, give a name to the deployment and hit **Create**.
![alt-text](/images/50_low_no_code_ml_Lab/auto-ai-4.gif?classes=shadow)

1. It will take a couple of minutes for the deployment. The status should be Deployed per below.
![alt-text](/images/50_low_no_code_ml_Lab/model-deployed.png?classes=shadow)

1. Click on model-deploy and you should see the Endpoint and Code Snippets per below.

{{% notice tip %}}
Copy the Endpoint URL as it will be used in subsequent steps.
{{% /notice %}}

![alt-text](/images/50_low_no_code_ml_Lab/model-endpoint.png?classes=shadow)

19. Lets do some predictions. Click on **Test** tab and input the data using form or Json format.
![alt-text](/images/50_low_no_code_ml_Lab/input-data-pred.png?classes=shadow)

1. Enter the input data using single or multiple samples (Json). We will try with single sample by giving the input to Region as Brussels & 100 as `Total_cases` and click on Add to list.
![alt-text](/images/50_low_no_code_ml_Lab/input-model.png?classes=shadow)

1. You should see the Input list updated with the sample values. Hit Predict to generate predictions.
![alt-text](/images/50_low_no_code_ml_Lab/pred-output.png?classes=shadow)

1. You can see the predicted value is 1 under Result section which means the risk index is predicted as Low for the input data of Brussels Region with 100 cases on a given day.

You have learnt how to build AI predictive models without any code, deploy the model and generate predictions. Feel free to play around to get comfortable using AutoAI for generating accurate predictions.
