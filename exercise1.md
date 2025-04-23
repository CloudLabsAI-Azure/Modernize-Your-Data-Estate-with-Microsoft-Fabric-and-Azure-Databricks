### Exercise 1: Data Engineering/Data Factory experience - Data ingestion from a spectrum of analytical data sources into OneLake
<!--
   *Before we start executing the steps, we will open a backup Click-by-Click lab using the following hyperlink in a new tab and navigate back to the VM browser:* 

   [Click-by-Click](https://regale.cloud/Microsoft/viewer/3088/modern-analytics-with-microsoft-fabric-copilot-and-azure-databricks-dream-lab-fu/index.html#/0/0) -->

   *Now, let's trigger the Simulator App to start streaming data to EventHub (**to be used later in exercise 4**).*

1. Open a **Microsoft Edge browser** from VM desktop.

2. Click on browser address bar and click **<inject key= "WebAppBrowse" enableCopy="true"/>** to browse app service and press **Enter**.

   >**Note**: **Do not click anywhere else on the screen until all of the text has been auto-filled.**

3. **IMPORTANT!!** PROCEED WITH THE NEXT STEPS 
    WHILE THIS LOADS.


   ![](media/labMedia/task-1.3.png)

### Task 1.1: Create a Microsoft Fabric enabled workspace

In this exercise, you will act as the Data Engineer, Eva, to transfer Contoso's data from Azure SQL Database into the Lakehouse and initiate data preparation for the upcoming merger between Contoso and Litware Inc.

1. Open **Microsoft Fabric** in a new tab by copy pasting the below link.

   ```BASH
   https://app.fabric.microsoft.com/home
   ```

2. Sign in with your Azure AD credentials. If you are not already signed in, you will be redirected to the Microsoft Fabric login page.

   >**Note:** Close any pop-up that appears on the screen.

   ![](media/image%20(5).png)

3. From the left navigation pane, click on **Workspaces** and then the **+ New workspace** button.

	![task-1.1.2.png](media/labMedia/task-1.1.2.png)

4. Type the name **<inject key= "WorkspaceName" enableCopy="true"/>**, **validate** the availability of the name, and click on **Advanced**.

   >**Note:** Only use the workspace name provided above.

   >**NOTE:** If the name **<inject key= "WorkspaceName" enableCopy="false"/>** is already taken, refresh the page and check again. A workspace with that name may already be created. If so, add a different suffix until the name is available.

   ![works-apply.png](media/labMedia/workspace01.png)

5. Ensure **Fabric capacity** is enabled, verify that **techconnectnorthcentralus - North Central US** is selected under **Capacity**, and then click **Apply**.

   ![works-apply.png](media/labMedia/workspace02.png)

   >**Note:** Close any pop-up that appears on the screen.

   ![gotit-popup.png](media/labMedia/gotit-popup.png)

   ![gotit-popup.png](media/labMedia/gotit-popup.1.png)

   >**Note:** Wait for the Power BI Workspace to load.

<!-- >**Note**:  If you see the pop message **Upgrade to Power BI Pro License** perform the following steps. Otherwise, skip to the next exercise.

10. *Click on the **Try free** button.*
   ![task-1.1-new2.png](media/labMedia/task-1.1-new2.png)

11. *Click on the **Got it** button to continue.*
   ![task-1.1-new3.png](media/labMedia/task-1.1-new3.png) -->

<!-- 12. Click on **Workspaces** to verify if the workspace with the given name was created, if not perform the steps above again.

>**NOTE:** If the workspace you created is not visible, perform **step 8** again. -->
<!-- 
![task-1.1-new4.png](media/labMedia/task-1.1-new4.png) -->


   
<!-- >**Note:** Click on the collapse icon, as shown in the screenshot below, for better visibility.

![collapsedicon.png](media/labMedia/collapsedicon.png) -->

### Create/Build a Lakehouse

Now, let's see how each department can easily create a Lakehouse in the Contoso workspace without any provision. They simply provide a name, given the proper access rights of course!
<!--

1. Click on the **experience** button at the **bottom left** corner of the screen (In this screenshot, **Power BI** is selected as an "Experience") and then Select **Fabric**.

    ![](media/labMedia/f1.png)

   >**Note:** Close any pop-up that appears on the screen.

   ![](media/image%20(5).png) -->

1. Click on the **three dots (ellipsis)** below the **<inject key= "WorkspaceName" enableCopy="false"/>** workspace and click on the **Create** icon.

   ![](media/labMedia/f2.png)
    

2. In the new window, under **Data Engineering**, click **Lakehouse**.

   ![task-wb2.png](media/labMedia/f3.png)

   **Note:** Screenshots in the exercises may sometimes differ from the actual lab. Please adjust your screen resolution to locate items and select them as needed.

3. Copy the name **lakehouse** from the following and paste it in the **Name** field.

   ```BASH
   lakehouse
   ```

4. Click on the **checkbox** and then click on the **Create** button.

   ![task-1.2.3.png](media/labMedia/task-1.2.3.png)

   **Note:** Expand the Lakehouse Explorer if it is collapsed.

   ![task-1.2.3.png](media/labMedia/task-1.2.3.1.png)

In just a few seconds, the Lakehouse is ready. With the right access, you, as a Data Engineer, can effortlessly create a new Lakehouse. There is no need to set up any storage accounts or worry about network, infrastructure, key vault, Azure subscriptions, etc.

---

### Task 1.2: Use the ‘New Shortcut’ option from external data sources

Now, this is something exciting! This section shows how easy it is to create Shortcuts without moving data. That is the power of OneLake! In this exercise, you will ingest the curated bounce rate data for Litware from ADLS Gen2 using the New Shortcut option. Let’s see how!

1. Click on the **three dots (ellipses)** on the right side of Files.

2. Click on **New shortcut**.

   >**Note:** Make sure you create a shortcut under **files** and not under **tables** in the lakehouse explorer pane.

   ![task-wb5.png](media/labMedia/task-wb5.png)

3. In the pop-up window, under **External sources**, select the **Azure Data Lake Storage Gen2** source.

   ![task-1.3-ext-shortcut4.png](media/labMedia/task-1.3-ext-shortcut4.png)

   >**Note:** Wait for the screen to load.

4. Select **Create new Connection** radio button..

5. In the following screen, we need to enter the connection details for the ADLS Gen2 shortcut.

   ![shortcut111.png](media/labMedia/task-1.3-ext-shortcut-11u.png)

6. Copy the **Data Lake Storage endpoint**: **<inject key= "storageEndpoint" enableCopy="true"/>** and paste it into the **URL** field.

7. Select **Organization account** in the **Authentication Kind**, and ensure you are signed in and click on **Next**.

    ![shortcut111.png](media/labMedia/task-1.3-ext-shortcut-111u.png)



9. Click on **Next** button.

10. Select the **data** and **litwaredata** checkbox and then click on the **Next** button.

    ![task-wb6.png](media/labMedia/task-wb6.png)

11. Click on the **Create** button.

      ![task-1.3-ext-shortcut10.png](media/labMedia/task-1.3-ext-shortcut10.png)

      And there you go! Your shortcut is now ready! 

12. Click (do not expand) on the newly created shortcut named **litwaredata**.

      ![task-wb7.png](media/labMedia/64.1.png)

Prior to Microsoft Fabric, departments in Contoso had to move the data they needed from other departments via time-consuming ETL processes. But look, now they have created shortcuts. No need to move any of this data. That is the power of OneLake!

### Task 1.3: Leverage Data Wrangler to profile and analyze data effectively and create Delta tables using Spark Notebook.

Now, let’s see how Data Engineer, Eva, Analyzed data by leveraging Data Wrangler and got the remaining data into OneLake by creating Delta tables using Spark Notebook. By using a Spark Notebook to create Delta tables, Eva can ensure more reliable, scalable, and efficient data management, which is essential for handling big data workflows.

1. Click on **<inject key= "WorkspaceName" enableCopy="false"/>** and select **New item**.

   ![task-wb8S.png](media/labMedia/64.2.png)

2. In the **New Item** tab, select **Notebook**.

   ![task-wb8S.png](media/labMedia/64.3.png)

   >**Note:**  If the pop-up appears click on **Skip tour** button.

   ![task-wb8S.png](media/labMedia/64.4.png)

3. Click on the **+ Data Sources** button and then select **Lakehouses**.

   ![task-wb8S.png](media/labMedia/64.5.png)

4. Select **Existing Lakehouse with Schema** and then click on the **Add** button.

    ![task-wb8S.png](media/labMedia/64.6.1.png)

5. Select the **lakehouse** and then click on **Add**

   ![task-wb8S.png](media/labMedia/64.7.png)

6.  Once the notebook is created, **hover below** the existing cell and click on **+Code** to create a new cell in the notebook. Paste the following **code** in the cell and **run** the cell.

    ![task-wb8S.png](media/f52.png)

      ```BASH
      import os
      # List all CSV files in the 'litwaredata' folder
      file_path = '/lakehouse/default/Files/litwaredata/'
      csv_files = [file for file in os.listdir(file_path) if file.endswith('.csv')]
      df_CustomerChurnData= spark.read.format("csv").option("header","true").load('Files/litwaredata/'+csv_files[0])
      df_dimcustomer= spark.read.format("csv").option("header","true").load('Files/litwaredata/'+csv_files[1])
      df_dimdate= spark.read.format("csv").option("header","true").load('Files/litwaredata/'+csv_files[2])
      df_dimproduct= spark.read.format("csv").option("header","true").load('Files/litwaredata/'+csv_files[3])
      df_dimreseller= spark.read.format("csv").option("header","true").load('Files/litwaredata/'+csv_files[4])
      df_factinternetsales= spark.read.format("csv").option("header","true").load('Files/litwaredata/'+csv_files[5])
      df_factresellersales= spark.read.format("csv").option("header","true").load('Files/litwaredata/'+csv_files[6])
      df_website_bounce_rate= spark.read.format("csv").option("header","true").load('Files/litwaredata/'+csv_files[7])
      ```

     > **Note:** Once the Spark code execution is completed, the output will appear as shown in the screenshot.

     ![task-wb8S.png](media/f53.png)

7. In the notebook ribbon **Home** tab, use the **Data Wrangler** dropdown and select any one of the dataframe.

   ![task-wb8S.png](media/f38New.png)

   > **Note** : If you can't see the Data Wrangler option, click the three dots (ellipsis) button.

   ![](media/labMedia/wrangler.png)

8. When Data Wrangler loads, it displays a descriptive overview of the chosen DataFrame in the **Summary** panel. Note that the table have no missing values and duplicate rows, similarly you can view data frames for other csv.

   ![task-wb8S.png](media/labMedia/f39.png)

9. Click on the **Back** arrow to return to the notebook.

   ![](media/f65.png)

10. Since the data is already normalized, we will load it into Delta tables. Create a **new cell** and paste the following **code** in it and **run** the cell.

      ```
      import os
      import pandas as pd
      
      # List all CSV files in the 'litwaredata' folder
      file_path = '/lakehouse/default/Files/litwaredata/'
      csv_files = [file for file in os.listdir(file_path) if file.endswith('.csv')]
      
      # Load each CSV file into a table
      for file in csv_files:
         table_name = file.split('.')[0]
         df = pd.read_csv(file_path + file)
         spark.createDataFrame(df).write.mode("ignore").format("delta").saveAsTable(table_name)
      ```

    ![task-wb8S.png](media/labMedia/64.8.png)

11. Once the execution is successful, **stop the Spark session**.

12. Click on **Lakehouse** in the left navigation pane.

    ![task-wb8S.png](media/labMedia/f64.png)

13. Expand **tables**, expand **dbo**, click on the **three dots**, and then click on **Refresh**. 

     ![task-wb8S.png](media/labMedia/64.10.1.png)

14. View the successfully **loaded tables**.

    ![task-wb8S.png](media/labMedia/f66.png)

15. Click on **website_bounce_rate** delta table and view the website bounce rate data.

     ![](media/labMedia/f67.png)

16. You now have all the tables in **OneLake** for Contoso to leverage. Next, we proceed with data transformation using Dataflow Gen2 to transform the sales data ingested from Litware. 




### Task 1.4: Leverage Dataflow Gen2 and Data pipelines for a "No Code-Low Code" experience to quickly ingest data with Fast Copy and transform it using Copilot

Using another great feature in Microsoft Fabric’s Data Factory, called Fast Copy, Contoso’s Data Engineer, Eva, quickly ingests terabytes of data with dataflows, thanks to the scalable Copy Activity in the pipeline. With so much data from Litware, there is bound to be a lot of clean up needed. Let’s step into Eva’s shoes to explore how she used fast copy to ingest data and Copilot to transform it, just in time to derive meaningful customer insights before their big Thanksgiving Sale!

You will experience how easy it is to use Fast Copy to transform 100M rows of Litware's sales data into the Lakehouse.


1. Click on **<inject key= "WorkspaceName" enableCopy="false"/>** and select **New item** then Click on **Dataflow Gen2**.

   ![task-1.3.1.png](media/labMedia/f9.png)

    

2. If prompted, uncheck **Enable Git integration, deployment pipelines and public API scenarios (preview)** box, click on **Create** or proceed to **step 3**.

    ![task-1.3.1.png](media/labMedia/f41.png)    

3. Click on the top part of the **Get data** icon (**not on the dropdown arrow at the bottom of the icon**).

      ![getdataSs.png](media/labMedia/getdataSs.png)

   **Note:** If the **Get data** option is not visible, click **New query** and then select **Get data**.
   
    ![getdataSs.png](media/labMedia/getdatau.png)

4. In the pop-up window, navigate to **OneLake Catalog**, select **Recommended**, and then choose **Lakehouse**.

   >Note: If the Lakehouse doesn't appear under **Recommended**, please wait for a while and then check again under both **Recommended** and **Recent**.

     ![task-1.2.04.S1.png](media/labMedia/task1.png)

5. If you see a screen similar to the following one, click on the **Next** button otherwise move to the next step.

   ![task-1.2.05.1.png](media/labMedia/task-1.2.05.1.png)

6. Expand **Files** and then expand **data**.

   ![task_1.4.5.png](media/labMedia/task_1.4.5.png)

7. Scroll down and select the **sales_data.csv** checkbox, then **click** on the **Create** button.

   ![task_1.4.6.png](media/labMedia/task_1.4.6.png)

8. Collapse the **Queries** pane and take a look at the sales dataset (**note that the first row of this dataset is not a header**).

   ![DFData.png](media/labMedia/DFData.png)

   > **Let's use Copilot to perform data cleansing.**

9. Click on the **Copilot** button, paste the following **prompt** in the textbox and click on the **send** icon.

   > **Note**: If the **Copilot** icon is not visible, click on the **Expand Ribbon** icon on the right side of the **Dataflow taskbar**. 

   ```
   In the table sales_data csv, apply first row as headers.
   ```

   ![df1a2.png](media/labMedia/df1a2u.png)

   >**Note:** If Copilot needs additional context to understand your query, consider rephrasing the prompt to include more details.

10. Scroll to the right-hand side and observe the **GrossRevenue** and **NetRevenue** columns. You'll notice the there are some empty rows with null values.

    ![DFData12.png](media/labMedia/DFData12.png)

    > **Let's use Copilot to remove empty rows.**

11. Similarly, paste the following prompt in Copilot and click on the **send** icon.

      ```
      Remove empty rows from GrossRevenue and NetRevenue columns.
      ```

    ![](media/labMedia/secondprompt2u.png)

12. Scroll to the right-hand side and observe the **GrossRevenue** and **NetRevenue** columns (**there are no empty rows with null values**).

    ![DFData13.png](media/labMedia/DFData13.png)

      >**Note:** Due to time constraints, we will not publish and run the Dataflow from the Pipeline.

      >**Note:** Expand the queries pane collapsed earlier.


<!-- 
13. Right click on the **Sales_data csv** under **Queries** and then select **Require fast copy**.


   >**Note:** If the **popup** does not appear, skip Step 14continue with Step 1 

   ![task_1.4.7.png](media/labMedia/task_1.4.7.png)
-->
<!--
14. Click on **Options**, scroll down to select **Scale** and tick **Allow use of fast copy connectors** checkbox then click on **OK**.

      **Note:** If **Allow use of fast copy connectors** checkbox is already checked click on **OK**.

      ![](media/56.png)
-->


13. Click on **Add data destination**, select **Lakehouse**.

     ![](media/57.png)

     > **Note** : If the **Add data destination** option is not visible, click on **Query** and then select **Add data destination**.

     ![](media/u58.png)

14. Click on **Next** button.

    ![](media/58.png)

15. Expand the workspace **<inject key= "WorkspaceName" enableCopy="false"/>**, and select **lakehouse**.

16. Enter the table name as **salesdataupdated** and then click on the **Next** button.

  	 ```BASH
      salesdataupdated
  	 ```

    ![](media/f55.png)

17. Click on the **Save settings** button.

    ![](media/60.png)

18. Click on the **Publish** button.

    ![](media/61.png)

Congrats on completing this data transformation exercise! 

Now let's use Copilot in Data pipeline to leverage the data transformation activities.

1. Click on the **<inject key= "WorkspaceName" enableCopy="false"/>** worspace at the **left** pane of the screen, then click on the **New item** button.

   ![task_1.4.1.png](media/labMedia/task_1.4.1.png)

2. Click on **Data pipeline**.

   ![task_1.4.10.png](media/labMedia/task_1.4.10.png)

3. Enter the name **pipeline** in the Name field and click on **Create** button.

   ```BASH
   pipeline
   ```

   ![task_1.4.11.png](media/labMedia/task_1.4.11.png)

4. Click on the **Copilot** icon in the top right corner of the screen.

   ![task_1.4.12.png](media/labMedia/task_1.4.12.png)

5. In the Copilot pane, click on the predefined option **Ingest data** and the following text will be populated in the prompt textbox.

   ```
   Get data using copy data activity
   ```

6. Click on **Send** icon.

   ![task_1.4.13.png](media/labMedia/task_1.4.13.png)

7. A **Copy Activity** is created and the next prompt text is loaded automatically in the text box.

   ![task_1.4.14.png](media/labMedia/task_1.4.14.png)

8. Replace the existing prompt by entering the following **prompt** in the textbox and click on **Send** icon.

   ```
   Source connection of "copy0" (Copy) is lakehouse;
   Destination connection of "copy0" (Copy) is lakehouse
   ```

   ![task_1.4.15.png](media/labMedia/task_1.4.15.png)

9. Replace the following **prompt** in the textbox and click on **Send** icon.

      ```BASH
      Table of Source connection "lakehouse" (Lakehouse) in "copy0" (Copy) is data/CampaignData/campaign-data.csv;
      table of Destination connection "lakehouse" (Lakehouse) in "copy0" (Copy) is dbo.CampaignData
      ```

      ![task_1.4.16.png](media/labMedia/task_1.4.16.png)

      >**Note:** If you see the message "Type / to show all connections," click on the **Source** tab, then select **lakehouse** and set the **Root Folder** to **Files**, and then run the above prompt again.

    ![task_1.4.16.png](media/labMedia/pipelineerror.png)

10. Click on the **Copy data** activity, scroll up the **Details pane**, click on the **Source** tab and click on the **Preview data**.

    ![task_1.4.17.png](media/labMedia/task_1.4.17.png)

11. Review the data and then click on the **Run this pipeline** option in the Copilot pane.

   ![task_1.4.18.png](media/labMedia/task_1.4.18.png)

   >Close the Preview data pop-up window.

12. Click on the **Save and run** button.

    ![task_1.4.19.png](media/labMedia/task_1.4.19.png)

13. **Wait** for the pipeline run to complete successfully.

    ![task_1.4.20.png](media/labMedia/f42.png)

14. Scroll up in the Copilot window to the top and select **Summarize this pipeline** option. The following text will be populated in the prompt textbox.

### Summarize this pipeline

15. Click on **Send** icon.

    ![task_1.4.21.png](media/labMedia/task_1.4.21.png)

16. Scroll down to review the summarization generated by Copilot.

    ![task_1.4.22.png](media/labMedia/task_1.4.22.png)

As you know, Litware was primarily using Azure Databricks with their data stored in ADLS Gen2 before the acquisition. Post merger, as one unified company – Contoso – they decided to leverage Azure Databricks to build and manage reliable data pipelines via Delta Live Tables (DLT). Now, you will see the amazing power of Unity Catalog that Contoso’s data architects used to quickly learn all about Litware's data without having to go through tons of documents. And all by simply leveraging AI and data intelligence.
