---
title: "8.1. Setup Data Source & Cognos Embedded Dashboard"
weight: 81
chapter: true
draft: false
---

# Setup Data Source & Cognos Embedded Dashboard

## Lab Steps:

> ### Step 1: Connect to Data Source

> In the Cloud Pak for Data Homepage, click **All projects** under **Projects** to visit Project page.

![](/images/20_trusted_ai_lab/recent_projects.png)

> Click New Project + and then click Next
![](/images/20_trusted_ai_lab/create_proj_1.png)

> Choose `Create an empty project`
![](/images/20_trusted_ai_lab/create_proj_1.1.png)

> Enter the name to project and then click Create
![](/images/20_trusted_ai_lab/create_proj_2.png)

> Once project is created then click 'New assets' and then select Connection to create connection with external data source.
![](/images/20_trusted_ai_lab/create_proj_3.png)
![](/images/20_trusted_ai_lab/create_proj_4.png)

> Select PostgreSQL from available connectors and provide connection details provided for Amazon Aurora PostgreSQL database credentials provided as part of Lab - 0.
![](/images/20_trusted_ai_lab/create_proj_5.png)
![](/images/20_trusted_ai_lab/create_proj_6.png)

> ### Step 2: Create a new Cognos Embedded Dashboard

> Before you get started, download the {{% button href="/files/lab1-dashboard.zip" icon="fas fa-download" icon-position="right" %}}lab1-dashboard.zip{{% /button %}} dashboard file and extract the zip file.

> Go back to the Cognos_Dashboard project created in previous step and then click 'Add to project' and then select asset type as Dashboard.

![](/images/20_trusted_ai_lab/create_proj_3.png)
 ![](/images/20_trusted_ai_lab/add-dashboard.png)

 > Select create a new dashboard from Local file, upload cognos-dashboard.json, provide a name to dashboard and click Create.

 ![](/images/20_trusted_ai_lab/upload_json_cognos.png)

 > ### Step 3: Relink Data Assets to the Dashboard

 > Once the dashboard is created, you will see a message saying Missing data asset (1/5).

  ![](/images/20_trusted_ai_lab/missing_import_cognos.png)

  > To relink the ts_regional_risk_index_table, follow below steps.

  ![](/images/20_trusted_ai_lab/relink-1.png)

  > Similarly follow the same steps to relink :
      ts_wallonia_region_table
      ts_flanders_region_table
      ts_brussels_region_table
      flanders_cases_prediction_table

  > ### Dashboard
  Once all the assets are relinked, you will see the dashboard view as shown.

  ![](/images/20_trusted_ai_lab/final_dashboard-1.2.png)
  >
