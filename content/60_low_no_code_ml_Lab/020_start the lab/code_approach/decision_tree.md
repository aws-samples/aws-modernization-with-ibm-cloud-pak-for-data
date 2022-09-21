---
title: "2.3. Run Decision Tree Notebook"
weight: 35
chapter: true
draft: false
---

# Run Decision Tree Notebook

{{% notice info %}}
In this lab exercise, you will learn a popular machine learning algorithm, Decision Tree. You will use this classification algorithm to build a model from historical data of region and their total cases. Then you use the trained decision tree to predict the Risk Index of a region.

{{% /notice %}}

## Notebook 3 : Risk Index Prediction with Decision Tree

- In Cloud Pak for Data, click on the **Assets** tab on top, under **Asset types** expand the **Source code** tab and select **Notebook**.

- You will see the three notebooks listed. You will refer to the **Region-All-Decision-Tree.ipynb** notebook.

- Click on the **three dot** menu and select **edit** to get started.

  ![brussels-edit](/images/50_low_no_code_ml_Lab/edit-nb-3.gif?classes=shadow)

- The notebook should look something as shown below.

  ![notebook-preview](/images/50_low_no_code_ml_Lab/notebook3-preview.png?classes=shadow)

- Before running the notebook, you need to add the S3 connection to the notebook.
  - Click on the third code cell in the notebook.
  - Click on **find and add data** button on top right.
  - Click on **Connections** tab.
  - You will see your connection variable. Click on **Insert to code** and select **pandas DataFrame**.
  - Select the **RI-data-ML.csv** dataset from the connection variable.

  ![add-data-connection](/images/50_low_no_code_ml_Lab/add-data-connection-nb3.gif?classes=shadow)

- Verify the dataframe name to be `data_df_1` in the generated code snippet.

- Click on **Cell** and select **Run All** to run the notebook.

  ![run-notebook](/images/50_low_no_code_ml_Lab/notebook3-run-all.png?classes=shadow)

- This will run the notebook, it will take some time please be patient.

- Once the notebook is completed you can observe the following in the notebook:
  - **Decision Tree Model Accuracy**
  - **Decision Tree Visualization**

- **Decision Tree Model Accuracy:** You can observe the accuracy of the model is 86.63%.

  ![nb2-current-trend](/images/50_low_no_code_ml_Lab/dt-accuracy.png?classes=shadow)

- **Decision Tree Visualization:** You can observe the decision tree in the notebook.

  ![nb2-lstm-accuracy](/images/50_low_no_code_ml_Lab/dt.png?classes=shadow)

You have successfully completed this lab exercise.

{{% notice info %}}
Next steps - [Visualize the Data in Cognos Embedded Dashboard](/50_lab_4/020_start-the-lab/visualize/)
{{% /notice %}}
