---
title: "4. Create a data module for Risk index and PII dashboard"
weight: 45
chapter: true
draft: false
---

# Create a data module for Risk index and PII dashboard

1. From the main dashboard, select the **+** icon in the lower left corner. Select **Data module** as shown below. 

![data-module](/images/40_visualization_and_insights_lab/data-module.png?classes=shadow)

2. From the source selection panel, click on **Data server and schemas** tab. Click the **postgreSQL** connection that you have created in step 2. Select the **public** folder and click on **OK**. This will open **Add tables** panel. In the **Add tables** panel select **Select tables** and click on **Next**. Select the tables mentioned below and click on **OK**.

![tables](/images/40_visualization_and_insights_lab/tables.png?classes=shadow) 

3. You will be redirected to a **New data module** panel. Select the **Relationships** tab as shown below to view the files in the graphic editor. At this point, no relationships will exist.

![relationships](/images/40_visualization_and_insights_lab/relationships.png?classes=shadow) 

4. Follow the steps below to create relationships.

![relationships-steps](/images/40_visualization_and_insights_lab/relationships-steps.gif) 

5. Similarly do a join for all the tables, for matched columns. The end result should result in the following:

![relationships-all](/images/40_visualization_and_insights_lab/relationships-all.png?classes=shadow) 

6. Click the **Save** icon in the top menu to save off the **Data module** and give appropriate name.
