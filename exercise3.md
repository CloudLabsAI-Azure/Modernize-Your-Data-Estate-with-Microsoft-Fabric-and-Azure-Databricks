
### Exercise 3: Power BI Experience in Microsoft Fabric

With the wide spectrum of data sources and Litware's data in OneLake, it is now time to get some awesome insights and visualizations from this data. Let's dive deep into the experience of the Business Analyst, Wendy, and do just that.
 
### Task 3.1: Create a Semantic model and generate insights using Copilot for Power BI

Based on all the gathered data, Wendy is expected to create Power BI reports for other data citizens and stakeholders. Let's step into her shoes to experience the power of Copilot for Power BI in conjunction with Direct Lake Mode.

1. Navigate back to the **Microsoft Fabric tab** on your browser.

2. Click on **Workspaces** and select **<inject key= "WorkspaceName" enableCopy="false"/>**.

   ![task-1.3.02.png](media/labMedia/l14.png)

3. Click on **Filter** and select **Lakehouse**.

   ![task-1.3-ext-shortcut1.png](media/labMedia/task-1.3-ext-shortcut1.png)

4. Click on the **lakehouse**.

    >**Note:** There are 3 options for lakehouse, namely Lakehouse, Semantic model (Default) and SQL endpoint. Make sure you select the **Lakehouse** option.

    ![task-wb11.png](media/labMedia/task-wb11.png)

5. Click on the **New semantic model** button. 

   ![task-new4.png](media/labMedia/task-new4.png)

6. In the **Direct Lake semantic model name** field, enter **website_bounce_rate_model**.

   ```BASH
   website_bounce_rate_model
   ```

7. Select workspace as **<inject key= "WorkspaceName" enableCopy="true"/>** and click on **expand icon** next to **dbo** checkbox.

   ![task-new5.png](media/labMedia/task-new5.png)

8. Click on **expand icon** next to **Tables** checkbox.

   ![task-new5.1.png](media/labMedia/task-new5.1.png)

9. Scroll down if you see a scroll bar and select **website_bounce_rate** table and click on the **Confirm** button. 

    ![task-new6.png](media/labMedia/task-new6.png)

   >Wait for the semantic model creation.

10. Click on the **<inject key= "WorkspaceName" enableCopy="false"/>** from the left navigation menu, click on **Filter** and under **Type** select **Semantic model.**

11. Click on **website_bounce_rate_model** semantic model.

    ![task-new6.png](media/labMedia/f56.png)

12. To create a new report using this semantic model, Click on **three dots ...** and click on **Create report**.

    ![task-new7.png](media/labMedia/f58.png)

    > **Note**: If you get a popup prompting you to upgrade to a Paid **Power BI Pro license**, simply click on the **Try free** button to activate the **Power BI Pro trial**, and click on **Got it**.

    ![task-new7.png](media/labMedia/tryfree.png)

13. Click on **Settings** icon and select **Power BI settings** from the 'Resources and extensions' section.

    >**Note:** If the settings icon is not visible, click on the three dots next to Profile icon and select Settings.

    ![task-new6.1.png](media/labMedia/task-new6.1.png)

14. Select **Semantic models** tab and select your Semantic model.

    ![task-new6.2.png](media/labMedia/task-new6.2.png)

15. Scroll down to **Q&A** section and expand it, then select **Turn on Q&A to ask natural language questions about your data** checkbox, and click on **Apply**.

    ![task-new6.3.png](media/labMedia/task-new6.3.png)

16. Click on **Untitled report** from the left pane.

    ![task-new6.3.png](media/labMedia/qna1.png)

17. Click on the **Copilot** icon and collapse the other panes named **Filters**, **Visualizations** and **Data**.

    ![task-new6.4.png](media/labMedia/task-new6.4.png)

    >**Note:** Close any pop-up that appears on the screen.

    ![coplitclose.png](media/labMedia/coplitclose.png)

18. Enable the **Preview** button and click on the **Get started** button.

    ![task-new6.5.png](media/labMedia/task-new6.5.png)

    You will now see how easy it is for the data analyst to create compelling Power BI reports and get deep insights with literally no hands-on coding!
	
19. Click on the **Prompt Guide** button.

    ![promptguide.png](media/labMedia/promptguide.png)  

20. Select the option **What's in my data?**

    > **Note:** If you don't see the 'What's in my data?' option, click in the **Copilot chatbox** field, enter the following prompt, and click the **Send** button: : 

    ![promptguide2.png](media/labMedia/promptguide2.png)

    The first option, 'What’s in my data?' provides an overview of the contents of the dataset, identifies and describes what’s in it and what the attributes are about. So, there’s no need to wait for someone to explain the dataset. This improves the efficiency and volume of report creation.

    ![promptguide2.1.png](media/labMedia/promptguide2.1.png)

21. Click on the Copilot chat box field and enter the prompt below.

      ```
      Create a report Bounce Rate analysis, to show the correlation between customer sentiment, particularly among millennials and Gen Z, unsuccessful product searches across different devices, and the website's bounce rate by customer generations.
      ```  

    >**Note:** Wait for the prompt to populate.

22. Click on the **Send** button and wait for the results to load. 

    ![query01.png](media/labMedia/query01.png)
	
    >**Note:** 
    - If you see the error message saying, 'Something went wrong.', try refreshing the page and restart the task. Being in a shared environment, the service may be busy at times.
    - If Copilot needs additional context to understand your query, consider rephrasing the prompt to include more details.

    >**Note:** The responses from Copilot may not match the ones in the screenshot but will provide a similar response.

    ![report.png](media/labMedia/report.png)

Based on this report, we notice that the website bounce rate for Contoso is especially high amongst the Millennial customer segment. Let’s ask Copilot if it has any recommendations for improving this bounce rate based on the results and data in the report.

We’ll ask Copilot for suggestions based on the results and data in the report. 

23. Enter the following prompt in Copilot, and press the **Send** button.

    ```
    Based on the data in the page, what can be done to improve the bounce rate of millennials?
    ```

	
    ![task-new13.png](media/labMedia/task-new13.png)
	
24. Look at the suggestions Copilot provided. Copilot creates the desired Power BI report and even goes a step further to give powerful insights. Wendy realizes that for the website bounce rate to improve, Contoso needs to transform their mobile website experience for millennials. This helps them reduce their millennial related customer churn too! Now, what if Contoso’s leadership team needed a quick summary of this entire report? **Smart Narrative** to the rescue! 
	
    ![task-new14.png](media/labMedia/task-new14.png)

<!--	
25. Expand the **Visualizations** pane and select the **Narratives** visual. 

    ![visualizations.png](media/labMedia/visualizations.png)

26. Click on the **Copilot (preview)** button within the visual.

    ![open-narrative.png](media/labMedia/open-narrative.png)
	
27. Select **Give an executive summary**. 

28. generated summary. See how easy it was to get an executive summary with absolutely no IT resource dependency!
 
    >**Note:** If you don't see 'Give an executive summary' option, click on the **Copilot narrative** chat box field, enter the prompt below, and click on **Update** :

      ```
      Summarize the data, provide an executive summary, indicating important takeaways.
      ```

    ![task-new16.png](media/labMedia/task-new16.png)

29. Expand the **narrative** from the corner to get a better readable view of the result.

    ![expand-arrow.png](media/labMedia/expand-arrow.png)

30. Click on the **Close** button in the pop-up window.

    ![close-copilot.png](media/labMedia/close-copilot.png)
	
The summary could also be generated in another language, if specified. Additionally, the summary updates if you filter the report on any visual.
-->