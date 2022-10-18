---
title: "Know more about the Notebooks"
weight: 50
chapter: false
draft: false
pre: "<b>B. </b>"
---


**Data-pre-processing.ipynb**

This notebook built in SageMaker takes care of all the pre-processing activities like **Data analysis, Merging datasets, Missing values, Feature engineering, Usecases formation** & more. The updated csv files are uploaded onto S3 bucket programmatically. 

**RI-SageMaker-Deploy-Wstudio.ipynb**

This notebooks builds a SageMaker Linear Learner predictive model for Risk Index prediction and deploys an endpoint on SageMaker platform. 

**Drift-Detection-Model.ipynb**

This notebook sets up the Drift metrics in the Watson OpenScale dashboard to monitor the SageMaker endpoint for **Drift** in data and model performance.

**SageMaker-Monitor-OpenScale.ipynb**

This notebook sets up IBM DB2 & the Watson OpenScale dashboard programmatically for monitoring and configuring metrics like **Fairness & Bias** in the SageMaker endpoint. 


**Optional** :- The below notebooks can be explored offline. 


**Risk_Index_Prediction.ipynb**

This notebook built using SageMaker Linear Learner (in-built module) takes care of building multi-class classification ML model for prediction risk index per region. Upload the **Notebook** into Cloud Pak for Data environment using Watson Studio in the next step. Try uploading this notebook offline using the instructions. 

**WS-Flanders-Predict.ipynb** & **WS-Belgium-Predict.ipynb**

These notebooks built in SageMaker using **Deep Neural Networks** takes care of building time-series forecasting models at the Region & Country levels. Upload the **Notebooks** into Cloud Pak for Data environment using Watson Studio in the next step. Try uploading these notebooks offline using the instructions. 
