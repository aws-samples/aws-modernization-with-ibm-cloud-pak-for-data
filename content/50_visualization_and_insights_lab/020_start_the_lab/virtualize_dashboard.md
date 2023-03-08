---
title: "6. Create and visualize IBM Cognos Analytics dashboard"
weight: 65
chapter: true
draft: false
---

# Create and visualize IBM Cognos Analytics dashboard

IBM® Cognos® Analytics integrates reporting, modeling, analysis, dashboards, stories, and event management so that you can understand your organization data, and make effective business decisions. After the software is installed and configured on Cloud pak for data, administrators set up security and manage data sources.

In this section we will use a Dashboard module which provides users a way to communicate insights and analysis of their data. A dashboard view contains visualizations such as graphs, charts, plots, table, maps, or any other visual representation of data.

### Create a Dashboard

1. From the Cognos Analytics home page, select the **+ New** icon in the lower left corner. Select **Dashboard**. Select the default template and click on **Create**.

2. Click **Select a source** and Select the **Data module** you just created in the previous section, and click **Add**.

![SelectSourceDM](/images/40_visualization_and_insights_lab/SelectSourceDM.png?classes=shadow) 

3. Now you should see a blank canvas to create your dashboard.

![DashBoardTables](/images/40_visualization_and_insights_lab/DashBoardTables.png?classes=shadow) 

4. In order to build a dashboard, one should be aware of the tools and icons how to use.

![DashBoardTools](/images/40_visualization_and_insights_lab/DashBoardTools.png?classes=shadow)

From the image above:

- [1] Toggles you between edit and preview mode.
- [2] Toggles display of the resouces (data objects) in the data module.
- [3] An example of one of many drop-down menus associated with data objects.
- [4] Displays the relationship between all of the visual objects on your dashboard. Objects with the same number are related.
- [5] Toggles full-screen mode on and off.
- [6] Toggles display of the filter panels.
- [7] Displays the fields associated with the selected visual object.
- [8] Displays the properties associated with the selected visual object.
- [9] Filters that can be applied to dashboard visual objects. The filter can be set for all dashboard tabs (left side), or for the current tab (righ side).

5. There are different types of visualizations available for us to consume. See below screenshot for reference.

![charts](/images/40_visualization_and_insights_lab/charts.png?classes=shadow)

### Add visualizations to the dashboard

### Risk Index Chart

Our first visualization will be a Map containing "Risk Index for REGION". It will also serve as a filter - if a region is selected, all of the other visualizations on the dashboard will change its focus to that region. Example, if we select 'Belgium' region, then the rest of the widgets in the dashboard will filter for that region.

1. Select **'REGION' and 'Risk Index' from the  -> ts-data-region_mod** in the resource list and drag it onto the canvas.


![RiskIndexWidget](/images/40_visualization_and_insights_lab/RiskIndexWidget.png?classes=shadow)

2. Use the box sizing tools to position the box in the upper left-hand corner of the dashboard.

3. Use the **Expand/Collapse** button in the upper right-hand corner of your visualization to view in expanded or collapse the view in your dashboard canvas.

4. Now, you can play with the properties for this widget. For example, we can disable the chart legend. See below screenshot for reference.
![DisableLegend](/images/40_visualization_and_insights_lab/DisableLegend.png?classes=shadow)

5. Using the same methods described for **Risk Index map widget**, change the title, axis labels, and color, etc..

### Summary Metrics Widget

1. Next we want to show the summary of metrics such as Total number of Active Cases bye region, Total deaths, Total Vaccination, Total tests done, etc..

2. From the available visualizations, drag and drop the **summary** vissualization onto the canvas. See below screenshot for refernce.

![SummaryWidget](/images/40_visualization_and_insights_lab/SummaryWidget.png?classes=shadow)

3. Select **CASES** field from the **Merged_HOSP_CAS** of the resource list. You will then see the total active covid cases for all the regions.
![ActiveCasesSummary](/images/40_visualization_and_insights_lab/ActiveCasesSummary.png?classes=shadow)


4. Similary create summary for others. Such as :

- Total Tests count from the Tests_Refined Resource list.

![TestsAll](/images/40_visualization_and_insights_lab/TestsAll.png?classes=shadow)
- Total Vaccination count from the Vaccination Resource list.

![Vacc](/images/40_visualization_and_insights_lab/Vacc.png?classes=shadow)
- Total Mortality/Deaths count from the Mortality Resource list.

![Mort](/images/40_visualization_and_insights_lab/Mort.png?classes=shadow)

### Cases by Gender and Age group

1. Similar to the **Risk Index** chart, we want to also show Covid analysis by Gender and Age group. 

2. Firstly drag and drop the pie chart visulaization on to the canvas, then
Select **Gender and Count** from Merged_HOSP-CAS resource and drag and drop on the pie chart.
![PieChartGender](/images/40_visualization_and_insights_lab/PieChartGender.png?classes=shadow)

3. Similaly, create a line chart for Total covid Cases by Age Group.
Drag and drop the Line chart visulaization on to the canvas, then
Select **Age Group and Count** from Merged_HOSP-CAS resource and drag and drop on the pie chart.
![LineChartAgeGroup](/images/40_visualization_and_insights_lab/LineChartAgeGroup.png?classes=shadow)

4. With the above knowledge, you should be able to create other widgets such as:

- PII details of the Hospital Staff
- Total cases by province
- Total number of covid tests and how many are positive out of those tests.


### Create a second tab for Data virtualization source data within the same dashboard

1. Click on **Add tab** to add more visualization using data virtualization as a data source.

![Tab2](/images/40_visualization_and_insights_lab/Tab2.png?classes=shadow)

2. Click **Select a source** and Select the **Data module** you created for data virtualization source, and click **Add**.

![DvDataSource](/images/40_visualization_and_insights_lab/DvDataSource.png?classes=shadow)

3. After you add the data virtualization data source, you should be able to create widgets similar to the above steps.
See the below widget for your reference which will help to create a similar one.

![DVDashboard](/images/40_visualization_and_insights_lab/DVDashboard.png?classes=shadow)

4. Once you complete the above widgets, Save the dashboard.

5. To convert the dahsboard visual theme, you could use the dashboard properties and select the Dark scheme from **Color and theme**tab.
See below screenshot for refernce.

![DarkMode](/images/40_visualization_and_insights_lab/DarkMode.png?classes=shadow)


Congratulations! You have completed your first Cognos Analytics dashboard. The layout and values should look similar to this:

![FinalDashboard](/images/40_visualization_and_insights_lab/FinalDashboard.png?classes=shadow)

{{% notice note %}}
NOTE: At any time, you can click on the **Edit or preview** button in the main menu bar to toggle between edit and preview mode. Click on **Preview** mode to get a better look at our current dashboard. 

When toggling back to **Edit** mode, you may have to click the **Data** icon (**0111**) to display the resource list.
{{% /notice %}}
