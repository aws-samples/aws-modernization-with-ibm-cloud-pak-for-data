---
title: "2. Code Approach"
weight: 20
chapter: true
draft: false
---

# Code Approach

In the Code Approach you will learn how to build two types of prediction models in Watson Studio's Jupyter Notebooks. As a Developer you will have full control over the model's hyperparameters and the training data in this section.

{{% notice info %}}
What are Hyperparameters?
A hyperparameter is a parameter whose value is used to control the learning process in a Machine Learning Algorithm. The same kind of machine learning models can require different constraints, weights or learning rates to generalize different data patterns. Hence we tune or optimize the hyperparameters so that the model can optimally solve the machine learning problem.
{{% /notice %}}

You will be using the following notebooks in this section:

- **Region-Brussels-LSTM.ipynb**
- **Region-Wallonia-LSTM.ipynb**
- **Region-All-Decision-Trees.ipynb**

- The LSTM notebooks are used to build the prediction models to predict future COVID-19 cases for Brussels and Wallonia region respectively. LSTM models are built using the data from the datasets in the S3 bucket. Both the models are built with different hyperparameters.

- LSTM Model for **Brussels** region is built with the following hyperparameters:
  - **train_test_split:** `0.70`
  - **lookback:** `30`
  - **hidden_layers:** `2`
  - **units:** `55`, `100`
  - **dropouts:** `0.15`, `0.15`
  - **optimizer:** `adam`
  - **learning_rate:** `0.001` (default)
  - **epochs:** `25`
  - **batch_size:** `32`

- LSTM Model for **Wallonia** region is built with the following hyperparameters:
  - **train_test_split:** `0.70`
  - **lookback:** `30`
  - **hidden_layers:** `2`
  - **units:** `60`, `100`
  - **dropouts:** `0.15`, `0.15`
  - **optimizer:** `adam`
  - **learning_rate:** `0.001` (default)
  - **epochs:** `25`
  - **batch_size:** `32`

- Aditionally, Decision Tree notebook is used to build a model to predict the Risk Index for Brussels, Flanders and Wallonia region.

- Decision Tree models are built with the following hyperparameters:
  - **train_test_split:** `0.70`
  - **max_depth:** `4`
  - **min_samples_split:** `2`
  - **min_samples_leaf:** `1`
  - **criterion:** `entropy`

#### The section is divided into following sub-sections:

{{% children showhidden="false" %}}
