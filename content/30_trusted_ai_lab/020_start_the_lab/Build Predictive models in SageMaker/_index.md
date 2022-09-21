---
title: "1. Build Predictive models in SageMaker"
weight: 10
chapter: false
draft: false
---

> #### Note:
> Data (COVID19BE_HOSP.csv & COVID19BE_CASES_AGESEX.csv) required for this lab has been uploaded to Amazon S3 bucket as the part of infrastructure automation. Update the bucket name from Lab 0 steps and use the BUCKET_REGION as `us-east-2`.

**You can use the predictive models built in SageMaker to continue with the steps per below.**

Login to the SageMaker console and click on Notebook instances under Notebook in the navigation pane.

![](/images/20_trusted_ai_lab/sm-login.png)

Click on create notebook instance, give it at name like Lab1, select the Notebook instance type as `ml.t2.medium`, Platform Identifier as `Amazon Linux 1, Jupyter Lab 1` & IAM role as shown below. It will take a couple of minutes for the instance to be created. Be patient!

![](/images/20_trusted_ai_lab/crt-nb-sm.png)

After the instance is created, click on open Jupyter. You can also open JupyterLab if needed.

![](/images/20_trusted_ai_lab/opn-nb-sm.png)

Click on `Upload` on the top right side to upload notebooks. **Download all the notebooks {{% button href="/notebooks/Notebooks.zip" icon="fas fa-download" icon-position="right" %}}Notebooks.zip{{% /button %}} into your local file system and unzip the file. You can upload all the notebooks in one go by clicking on UPLOAD option and run them in SageMaker. Make sure to update the Region, Access Key & Secret Key in the notebooks wherever specified before running the notebooks.**

**Select the Kernel as `conda_python3` when prompted and choose `Set Kernel` option.**

**After uploading the notebooks, update the AWS credentials, click on `Kernel` and choose `Restart & Run All` option.**

When a notebook is executed, what is actually happening is that each code cell in
the notebook is executed, in order, from top to bottom.

Each code cell is selectable and is preceded by a tag in the left margin. The tag
format is `In [x]:`. Depending on the state of the notebook, the `x` can be:

* A blank, this indicates that the cell has never been executed.
* A number, this number represents the relative order this code step was executed.
* A `*`, this indicates that the cell is currently executing.

**There are several ways to execute the code cells in your notebook:**

* One cell at a time.
  * Select the cell, and then press the `Play` button in the toolbar.
* Batch mode, in sequential order.
  * From the `Cell` menu bar, there are several options available. For example, you
    can `Run All` cells in your notebook, or you can `Run All Below`, that will
    start executing from the first cell under the currently selected cell, and then
    continue executing all cells that follow.**

If you want to download the notebooks, select the notebook - click on File - Download as - Notebook(.ipynb) into your local file system.

![](/images/20_trusted_ai_lab/dw-nb-sm.png)
