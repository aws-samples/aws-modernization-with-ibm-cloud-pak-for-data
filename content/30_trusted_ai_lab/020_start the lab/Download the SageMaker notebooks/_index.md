---
title: "3. Download SageMaker notebooks and import them into IBM Watson Studio (Cloud Pak for Data)"
weight: 10
chapter: false
draft: false
---


#### The Notebooks have been created in SageMaker and was downloaded in Step 1. You can refer to the Notebooks folder and get going with next steps.

**Data Pre-processing**

Navigate to the notebooks folder in your local file system and select the notebook **Data-pre-processing.ipynb**. This notebook built in SageMaker takes care of all the pre-processing activities like **Data analysis, Merging datasets, Missing values, Feature engineering, Usecases formation** & more. The updated csv files are uploaded onto S3 bucket programmatically. Upload the **Notebook** into Cloud Pak for Data environment using Watson Studio in the next step.

**Risk Index Prediction**

Navigate to the notebooks folder in your local file system and select the notebook **Risk_Index_Prediction.ipynb**. This notebook built using SageMaker Linear Learner (in-built module) takes care of building multi-class classification ML model for prediction risk index per region. Upload the **Notebook** into Cloud Pak for Data environment using Watson Studio in the next step.

**Time-Series Forecasting Models**

Navigate to the notebooks folder in your local file system and select the notebooks **WS-Flanders-Predict.ipynb** & **WS-Belgium-Predict.ipynb**. These notebooks built in SageMaker using **Deep Neural Networks** takes care of building time-series forecasting models at the Region & Country levels. Upload the **Notebooks** into Cloud Pak for Data environment using Watson Studio in the next step.
