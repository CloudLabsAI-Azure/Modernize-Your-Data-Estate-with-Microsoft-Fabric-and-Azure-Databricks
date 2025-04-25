### Exercise 4: Explore Data Science experience in Microsoft Fabric 
 
Microsoft Fabric offers Data Science experiences to empower users to complete end-to-end data science workflows for data enrichment and business insights. You can complete a wide range of activities across the entire data science process, all the way from data exploration, preparation and cleansing to experimentation, modeling, model scoring and serving predictive insights to BI reports.

### Task 4.1: Build ML models and experiments using Copilot in Microsoft Fabric

   ![task-3.1.1.png](media/labMedia/exercise5_1.1.png)

To understand the cause behind Contoso’s declining revenue, the team needed to dive deeper into their customers’ spending pattern.

Copilot responds to queries in natural language or generates customized code snippets for tasks like creating charts, filtering data, applying transformations, and building machine learning models.

Let’s see how Copilot for Notebook helps you, as a Data Engineer, quickly create Data Science Notebooks.


1. Click on the **<inject key= "WorkspaceName" enableCopy="true"/>** workspace from the left navigation pane.

   ![task-3.1.2.png](media/labMedia/exercise5_1.3.4.png)

   **Note:** Click on **Don't save** if this pop-up appears.

     ![task-3.1.2.png](media/labMedia/f59.png)

2. Click on **Import** dropdown, select **Notebook** and then select **From this computer**

   ![task-3.1.2.png](media/labMedia/f16.png)

   **Note:** If the Import option is not visible, click the **three dots (ellipsis)** button and select Import.

3. Click on the **Upload** button.

   ![task-3.1.2.png](media/labMedia/exercise5_1.3.1.png)

4. Browse to the fabricnotebooks folder in your VM  by following the path `C:\LabFiles\techconnect\artifacts\fabricnotebooks` and then select **Build ML models and experiments using Copilot for Data Science in Microsoft Fabric** notebook.

5. Click on the **Open** button.

   ![task-3.1.2.png](media/labMedia/exercise5_1.3.2.png)

6. Wait for the notebook to **upload**.

   ![task-3.1.2.png](media/labMedia/exercise5_1.3.3.png)


7. Click on **Filter**, expand **Type** and select **Notebook**.

   ![task-3.1.2.png](media/labMedia/exercise5_1.3.5.png)

8. Click on the **Build ML models and experiments using Copilot for Data Science in Microsoft Fabric** notebook.

   ![task-3.1.2.png](media/labMedia/exercise5_1.3.6.png)

9. Click on **+ Add data items** button and click on **Existing data sources**.

   ![task-3.1.2.png](media/labMedia/l15.png)

10. Select **lakehouse**, and click on **Connect** button.

    ![task-3.1.2.png](media/labMedia/l16.png)

11. Click on **Connect** dropdown in the Home Ribbon and click on **New standard session** to connect to a session.

    ![task-3.1.2.png](media/labMedia/standardsession.png)

11. Click on the **Copilot** button and then click on the **Get Started** button.

    ![task-3.1.2.png](media/labMedia/exercise5_1.6.png)

     **Note:** If the **Copilot** option is not visible, click the **three dots (ellipsis)** button and select Copilot.

12. "In the Explorer pane, click on the **ellipsis (three dots)** next to your lakehouse and select **Set as default lakehouse**.

    ![task-3.1.2.png](media/labMedia/l17.png)

13. Copy and paste the **below prompt** in the textbox.

      ```
      Please load "customerchurndata" table from the Lakehouse into a Spark DataFrame. Then convert that into pandas dataframe as df.
      ```

14. Click on the **send** button.

    ![task-3.1.2.png](media/labMedia/exercise5_1.8.png)

15. Click on the **Copy code** icon.

    >**Note:** The new cell will be created right above the cell.

    ![task-3.1.2.png](media/labMedia/exercise5_1.8.2.png)

16. Click on a **+ Code** above the first cell of the notebook.

    >**Note:** The new cell will be created right above the cell.

    ![task-3.1.2.png](media/labMedia/exercise5_1.8.1.png)

17. Paste the **copied query** and run the new **cell**.

     ![task-3.1.2.png](media/labMedia/exercise5_1.9.png)

    **Note:** Copilot may not respond as expected,please copy and paste the following code to obtain the result:

      ```
      # Load the table into a Spark DataFrame
      spark_df = spark.table('lakehouse.dbo.customerchurndata')
      
      # Convert the Spark DataFrame to a pandas DataFrame
      df = spark_df.toPandas()
      ```


With the data prepared with the help of Copilot, Data Scientists like you can explore the data to understand the patterns it contains.

The rest of the notebook has similar PySpark queries to explore customer churn prediction.

### Task 4.2: Predicting Customer Churn using New AutoML in Microsoft Fabric

1. Click on the **<inject key= "WorkspaceName" enableCopy="true"/>** workspace from the left navigation pane.

   ![task-3.1.2.png](media/labMedia/exercise5_1.3.4.png)

2. Click on **New item**, scroll down and select **Notebook**.

   ![task-3.1.2.png](media/labMedia/AutoMLf-19.png)

3. Click on the **notebook name** at the top corner and enter **Build ML models and experiments using AutoML** in the Notebook **Name** field. 

    > **Note:** Click anywhere on the screen to save to notebook name.

    ```BASH
    Build ML models and experiments using AutoML
    ```

   ![task-3.1.2.png](media/labMedia/AutoMLf-20.png)

4. Click on the **+ Add data items** button and then select **Existing data sources**.

   ![task-wb8S.png](media/labMedia/l18.png)


5. Select **lakehouse**, and click on **Connect** button.

   ![task-wb8S.png](media/labMedia/l16.png) 

6. Click on **New AutoML Run** icon.

   ![task-3.1.2.png](media/labMedia/AutoMLf-21.png)

    **Note :** If the **New AutoML Run** option is not visible, click the **three dots (ellipsis)** button and select **New AutoML Run**.

     ![task-wb8S.png](media/labMedia/u60.png)

7. Click on **lakehouse** and then click on the **Next** button.

   ![task-3.1.2.png](media/labMedia/f22.png)

8. Select **customerchurndata** table and click on the **Next** button..

    ![task-3.1.2.png](media/labMedia/f23.png)

9. Select **Binary Classification** and click on the **Next** button.

    ![task-3.1.2.png](media/labMedia/f24.png)

10. In **Choose prediction column** dropdown select **churn** and then click on the **Next** button.

    ![task-3.1.2.png](media/labMedia/f25.png)

11. Click on the **Next**.

     ![task-3.1.2.png](media/labMedia/f26u.png)

12. Review the Summary and the click on the **Create** button to generate AutoML notebook.

     ![task-3.1.2.png](media/labMedia/AutoMLf-22.png)

    >**Note:** Wait for 20 to 30 seconds for the notebook to load.

13. Since the data has already been normalized lets comment out function used for featurization, click on the notebook from the left navigation and scroll down in the Notebook to the **Step 2: Generate Features** section. Locate cell number 3 within this section, and comment out lines 11 by adding **#** symbol at the beginning of each line, as shown in the screenshot.

    ![task-3.1.2.png](media/labMedia/l19.png)

    ![task-3.1.2.png](media/labMedia/l20.png)

14. Click on **Run all** from the ribbon.

    ![task-3.1.2.png](media/labMedia/f33.png)

    **Note:** It takes approximately 5-8 min to complete execution.

15. Notice the cells as they get executed, **scroll down** to check next cell.

    ![task-3.1.2.png](media/labMedia/f34.png)

16. **Scroll down** and notice prediction results generated from the model.

    ![task-3.1.2.png](media/labMedia/f61.png)

17. **Scroll down** to the last cell, observe the prediction being saved in the table in OneLake.

    ![task-3.1.2.png](media/labMedia/f36.png)

### Task 4.3: Leverage AI skills for Q&A

AI Skill, a new capability in Microsoft Fabric, allows Data Analysts like Serena to create their own generative AI experiences. Serena believes that generative AI offers a transformative way to interact with data, significantly boosting data-driven decision-making in organizations worldwide. 

In this exercise, you’ll step into Data Analyst, Serena’s shoes and leverage AI Skill to create conversational question-and-answer (QnA) systems. 


1. Click on the **<inject key= "WorkspaceName" enableCopy="true"/>** workspace from the left navigation pane.

   ![task-3.1.2.png](media/labMedia/exercise5_1.3.4.png)

2. Click on **New item** and search for **Data agent**. select **Data agent(Preview)**.

    ![task-5.2](media/labMedia/l21.png)

3. In the **Create data agent** pop-up: Enter **Contoso-assistant** in the name field and click on **Create** button.

    ```BASH
    Contoso-assistant
    ```

    ![task-5.2](media/labMedia/l22.png)

4. In the Explorer pane, click on **+ Data source**, select **Lakehouse** from the available options, and then click **Add** to include it as a data source.

   ![task-5.2](media/labMedia/l23.png)

5. Click on **Refresh** button.

    ![task-5.2](media/labMedia/refresh9.png)

6. Under lakehouse dropdown, expand **dbo**, and select the following tables as shown in the screenshot.

    - dimcustomer
    - dimdate
    - dimproduct
    - dimreseller
    - factinternetsales
    - factresellersales

        ![task-5.2](media/labMedia/items.png)

    >**Note:** If the tables are not visible, hard refresh the VM browser using **Ctrl + Shft + R**.


7. Type **What is the most sold product?** in the chatbox and click on the **Send** icon.

    ```BASH
        What is the most sold product?
    ```

   ![task-5.2](media/labMedia/AIskill7.png)

    **Note:** This may take some time; wait until a response is received.

8. Data agent answered the question fairly well based on the selected tables.

   However, the SQL query needs some improvement, it orders the products by order quantity, when total sales revenue associated with the product is the most important consideration, as shown in the above screenshot.

   To improve the query generation, let's provide some instructions, as shown in these examples:

   ```
   Whenever I ask about "the most sold" products or items, the metric of interest is total sales revenue and not order quantity.

   The primary table to use is FactInternetSales. Only use FactResellerSales if explicitly asked about resales or when asked about total sales.
   ```

9. Copy the above notes and click on the **Data agent instrutions** paste it in **Data agent instrutions** box. Type **What is the most sold product ?** in the chatbox and then click on the **Send** button.  

    ```BASH
    What is the most sold product?
    ```

    Asking the question again returns a different answer, **Mountain-200 Black, 46**, as shown in the below screenshot:

    ![task-5.2](media/labMedia/AIskill8.png)

   In addition to instructions, examples serve as another effective way to guide the AI. If you have questions that your AI skill often receives, or questions that require complex joins.

10. Click on the **Example queries** In the Example queries click on **edit** icon.

    ![task-5.2](media/labMedia/l26.png)

11. Click on **+ Add Example**, enter the provided question along with its corresponding SQL query, and then click the **Close (X)** button.

     ![task-5.2](media/labMedia/l27.png)

    |Question| SQL query|
    |--------|----------|
    |who are the top 5 customers by total sales amount?|SELECT TOP 5 CONCAT(dc.FirstName, ' ', dc.LastName) AS CustomerName, SUM(fis.SalesAmount) AS TotalSpent FROM factinternetsales fis JOIN dimcustomer dc ON fis.CustomerKey = dc.CustomerKey GROUP BY CONCAT(dc.FirstName, ' ', dc.LastName) ORDER BY TotalSpent DESC;|

    >**Note** : After entering the first example and query, click the **+ Add Example** button.


12. Type **who are the top 5 customers by total sales amount?** in the chatbox and click on **Send** button.

    ```BASH
    who are the top 5 customers by total sales amount?
    ```

     ![task-5.2](media/labMedia/l28.png)

13. Click on **Publish**.

    ![task-5.2](media/labMedia/AIskill13.png)

14. In the pop-up screen click on the **Publish** button.

    ![task-5.2](media/labMedia/AIskill14.png)

15. Notice that AI skill is published successfully.

    ![task-5.2](media/labMedia/AIskill15.png)
