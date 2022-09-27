---
title: "Architecture Diagram"
weight: 10
chapter: false
draft: false
pre: "<b>A. </b>"
---

## This is the architecture diagram for this lab.

![architecture](/images/20_trusted_ai_lab/arch-flow.png?classes=shadow)


## Flow

1. Upload raw data from source to S3 bucket
2. Pre-process & analyze the data
3. Merge the data files to create consolidated date
4. Ingest the data from S3 bucket into SageMaker
5. Build multiple predictive models in SageMaker
6. Download the SageMaker models and import them into Watson Studio
7. Run the models in Watson Studio
8. Write the results back to S3 bucket
9. Generate visualizations using embedded dashboard
