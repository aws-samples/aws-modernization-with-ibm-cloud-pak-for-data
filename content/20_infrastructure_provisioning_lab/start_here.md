---
title: "Start Here"
weight: 25
chapter: true
draft: false
pre: '<i class="fa fa-flask" aria-hidden="true"></i> '
---

# Start Here

## Learning Objectives

- Prepare the environment for the immersionday upcoming lab exercise
  - Load data to Amazon S3, AWS Redshift and AWS RDS Aurora.
  - Create users in IBM Cloud Pak For Data
  - Generate credential to access the AWS services. 

<!-- -->
## Prerequisites
- IBM Cloud Pak for Data
- AWS Account

## Overview

This lab implements creating required infrastructure and loading data
onto respective AWS resources.

## Lab Environment

### Step 1: AWS Resources used in this lab
#### AWS Cloud9
**AWS Cloud9** is a cloud-based integrated development environment (IDE) that lets you write, run, and debug your code with just a browser. It includes a code editor, debugger, and terminal. Cloud9 comes prepackaged with essential tools for popular programming languages, including JavaScript, Python, PHP, and more, so you don’t need to install files or configure your development machine to start new projects. Since your Cloud9 IDE is cloud-based, you can work on your projects from your office, home, or anywhere using an internet-connected machine.

##### How we made it different?
In this cloud9 environment we have pre-installed with the required tools and utilities to access specific to our lab execution.

### Step 2: Cli Resources used in this lab
#### Openshift Cli
With the OpenShift command-line interface (CLI), the oc command, you can create applications and manage OpenShift Container Platform projects from a terminal. The **OpenShift CLI** is ideal in the following situations:

* Working directly with project source code

* Scripting OpenShift Container Platform operations

* Managing projects while restricted by bandwidth resources and the web console is unavailable

#### AWS CLI
The AWS Command Line Interface (AWS CLI) is a unified tool to manage your AWS services. With just one tool to download and configure, you can control multiple AWS services from the command line and automate them through scripts.

### Step 3: How to access the cloud9 environment?
Your instructor will provide you with the credentials to login. Access Cloud9 Environment through browser console.

1.  Set environment variable. 

        export OCP_USER=<<LAB INSTRUCTOR WILL SHARE VALUE>>
        export OCP_PASSWORD=<<LAB INSTRUCTOR WILL SHARE VALUE>>
        export OCP_API=<<LAB INSTRUCTOR WILL SHARE VALUE>>

2.  Run command to login to the cluster

        oc login --insecure-skip-tls-verify=true -u ${OCP_USER} -p ${OCP_PASSWORD} ${OCP_API}:6443

    **Expected Output:**

        Login successful.

        You have access to 66 projects, the list has been suppressed. You can list all projects with 'oc projects'


3.  Create users in CP4D cluster and **note down the user details**.

        ./create_users.sh

    **Expected Output:**

        Users created successfully.
        Password for both XXXXXXX and XXXXXXX is: XXXXXXX
        Providing access to service instances
        Giving user access to service instances - In Progress
        Giving user access to service instances - Done

4.  Get the route.

        oc get route -n zen |awk 'NR==2 {print $2}'

      Using the route, users will be able to login into CP4D using the above created credentials and start Lab exercises.

## Conclusions

1.  We have learned how to use the command line tools.

2.  We have learned how to access the openshift cluster and CP4D
    environment.

## Appendix

1. To print credentials, endpoints of Amazon S3, RedShift, Postgres attendees can run the below script.


        ./printcredentials.sh
