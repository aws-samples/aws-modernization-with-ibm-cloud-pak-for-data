---
title: "Cleanup"
weight: 80
chapter: true
draft: false
---

# Clean-up

{{% notice warning %}}
Only complete this section if you are running the workshop on your own.
{{% /notice %}}

{{% children %}}

## Learning Objectives

How to clean all **Immersion Day** infrastructure resources (IBM Cloud Pak for Data deployment and the Amazon EKS cluster) after finishing all lab.

## Steps to Cleanup Immersion Day resources

**Perform below steps only if you want to delete all Immersion Day infrastructure**

1. Login to AWS console and search for CloudFormation service.

2. Find the master **Stack** which you have created earlier and click **Delete** to delete stack.   
![](/images/delete_stack_1.png)

3. Click **Delete confirmation** dialog box. It may take a few minutes to delete entire cluster.

4. Verify your AWS account that all services deployed for Immersion Day has been terminated/deleted from your AWS account.

## Conclusions

1.  We have learned how to delete CloudFormation stack.
