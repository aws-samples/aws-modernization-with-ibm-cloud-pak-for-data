---
title: "3.1. Setup Cognos Embedded Dashboard"
weight: 45
chapter: true
draft: false
---

# Setup Cognos Embedded Dashboard

{{% notice info %}}
You need to create a new Dashboard in your Cloud Pak for Data project in order to visualize the analytical results. In this section you will learn how to setup a new Cognos Embedded Dashboard in your project.

{{% /notice %}}

## Create a new Cognos Embedded Dashboard

1. Before you get started, download the {{% button href="/dashboard/Covid-19-predictions-dashboard.zip" icon="fas fa-download" icon-position="right" %}}Covid-19-Predictions-Dashboard.json{{% /button %}} dashboard file and extract the zip file.

1. Go to Cloud Pak for Data projects, select your project.
1. Click on **New Asset**, under **Graphical builders** select **Dashboard editor**.

1. Select create a new dashboard from **Local file**.
  - Upload the `Covid-19-Predictions-Dashboard.json` extracted file.
  - Enter a **name** for the dashboard.
  - Click on **Create**.

## Relink Data Assets to the Dashboard

1. Once the dashboard is created, you will see a message saying **Missing data asset (1/8)**.

![relink](/images/50_low_no_code_ml_Lab/relink.png?classes=shadow)

1. To relink the missing data assets, do the following:
  - Click on Relink.
  - Select **Data Assets** and select the dataset.
  - Link the following data assets:
    - **Brussels.csv**
    - **brussels-actualVsPredicted.csv**
    - **brussels-errorEvaluation.csv**
    - **brussels-next7Prediction.csv**
    - **Wallonia.csv**
    - **wallonia-actualVsPredicted.csv**
    - **wallonia-errorEvaluation.csv**
    - **wallonia-next7Prediction.csv**

![re-link-data-asset2](/images/50_low_no_code_ml_Lab/re-link-data-asset2.gif?classes=shadow)

Once all the assets are relinked, you will see the dashboard view as shown.

![cognos-dashboard](/images/50_low_no_code_ml_Lab/cognos-dashboard1.png?classes=shadow)

More about the dashboard is explained in the next section.
