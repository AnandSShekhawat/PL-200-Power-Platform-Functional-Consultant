# Lab 1.6: Relationships

## Scenario

You are a Power Platform functional consultant and have been assigned to the Fabrikam project for the next stage of the project.

In this practice lab, you will be modifying the properties of existing relationships, creating new relationships, and creating rollup columns.

You will then export your customizations from the solution and import them into another environment.

## Lab objectives
In this lab, you will perform:

+ Exercise 1: Calculated and formula columns
+ Exercise 2: Change relationship behaviors
+ Exercise 3: Add new relationship
+ Exercise 4: Hierarchical relationship
+ Exercise 5: Project Outcome relationships
+ Exercise 6: Connections
+ Exercise 7: Calculated and rollup columns
+ Exercise 8: Solutions

## Exercise 1: Calculated and formula columns

In this exercise, you will create calculated and formula columns.

First, we will create columns based on a single table to calculate and show the estimated number of days in a project and concatenate project type and region as the project summary. We will make these configurations on the Project table.

### Task 1.1: Add a calculated column

1.  In the **Objects** pane on the left, expand **Tables**, and select **Project**.

1.  Under **Schema**, select **Columns**.

1.  Select **+ New column**.

1.  Enter `Length of Project` for **Display name (1)**.

1.  Enter `Number of days` for **Description (2)**.

1.  Select **Number** in the **Data type (3)** drop-down. The Data type will be set to **Whole Number** and the Format will be set to **None**.

1.  Change the **Behavior (4)** drop-down to **Calculated**.

1.  Select **Save and edit (5)**.

    ![Add calculated column.](../media/pl200-p8t1p1.png)

    > **Note:** You may need to disable the pop-up blocker in your browser first, then open the **Length of Project** column and select **Edit**.

1.  When a new browser window opens, select **+ Add condition**.

    ![Add calculated column.](../media/pl200-p8t1p2.png)

1.  Select **Scheduled Start** for **Field**.

1.  Select **Contains data** for **Operator**.

1.  Select the green check mark to save changes.

    ![Add calculated column.](../media/pl200-p8t1p3.png)

    > **Note:** You may need to resize the window to see the check mark.

1.  Select **+ Add condition**.

1.  Select **Estimated End** for **Field**.

1.  Select **Contains data** for **Operator**.

1.  Select the green check mark.

1.  Select **+ Add action**.

    ![Add calculated column.](../media/pl200-p8t1p4.png)

1.  Enter the following formula:

    ```DIFFINDAYS(contoso_scheduledstartdate,contoso_estimatedenddate)```

    > **NOTE:** You can use intellisense to type and select the elements in the formula.

1.  Select the blue check mark to save changes.

1.  Select **SAVE AND CLOSE**.

    ![Add calculated column.](../media/pl200-p8t1p5.png)


### Task 1.2: Add a formula column

1.  In the **Objects** pane on the left, expand **Tables**, and expand **Project**.

1.  Select **Columns** under **Project.**

1.  Select **+ New column**.

1.  Enter `Project Summary` for **Display name**.

1.  Select **Formula** in the **Data type** drop-down.

1.  Enter the following formula:

    ```Concatenate('Project Type'.Name,"|",Region.'Region Name')```

    > **NOTE:** You can use intellisense to type and select the elements in the formula.

1.  Select **Save**.    

## Exercise 2: Change relationship behaviors

In this exercise, you will be modifying the cascade relationships for the project table. The Region to Project relationship will be changed to referential, restricted and the Project to Milestone relationship will be changed to custom.

### Task 2.1: Region-Project relationship

1. Navigate to the Power Apps Maker portal `https://make.powerapps.com`

1. Make sure you are in your **PL Development** environment.

1. Select **Solutions**.

1. Open the **Fabrikam Environmental** solution.

1. In the **Objects** pane on the left, expand **Tables**.

1. Select the **Project** table.

1. Under **Schema**, select **Relationships**.

1. Scroll down and select the **Region** relationship.

1. In the **Many-to-one** pane that appears on the right-hand side of the screen, expand **Advanced options**.

1. Change the **Delete** drop-down to **Restrict (1)**.

1. Select **Done (2)**.

    ![Add calculated column.](../media/pl200-p8t1p6.png)

### Task 2.2: Project-Milestone relationship

1. In the **Project** table **Relationships**, select **Project** from the table. Note that this relationship uses **Project** as the Display name and **contoso_project_milestone** as the Name. 

1. In the **One-to-many** pane that appears on the right-hand side of the screen, expand **Advanced options (1)**.

1. Change the **Type of behavior** drop-down to **Custom (2)**.

1. Change the **Delete** drop-down to **Restrict (3)**.

1. Change the **Assign** drop-down to **Cascade Active (4)**.

1. Change the **Share** drop-down to **Cascade User-Owned (5)**.

1. Change the **Unshare** drop-down to **Cascade User-Owned (6)**.

1. Select **Done(7)**.

    ![Cascade relationship.](../media/pl200-p8t2p1.png)

## Exercise 3: Add new relationship

In this exercise, you will create a new relationship between the Resource and Project tables to create a lookup for the Lead Resource on the Project.

### Task 3.1: Create new Project Lead relationship

1. Navigate to the Power Apps Maker portal `https://make.powerapps.com`

1. Make sure you are in your **PL Development** environment.

1. Select **Solutions**.

1. Open the **Fabrikam Environmental** solution.

1. In the **Objects** pane on the left, expand **Tables**.

1. Select the **Project** table. 

1. Under **Schema**, select **Relationships**.

1. Select **+ New relationship (1)** and choose **Many-to-one (2)**.

    ![Cascade relationship.](../media/pl200-p8t3p1.png)

1. In the **Many-to-one** pane that appears on the right-hand side of the screen, select **Resource (1)** in the **Related (One)** drop-down.

1. Enter `Project Lead` for **Lookup column display name (2)**.

1. Enter `projectleadresourceid` for **Lookup column name (3)**.

1. Expand **General**.

1. Enter `resource_project_projectlead` for **Relationship name (4)**.

1. Expand **Advanced options**.

1. Change the **Delete (5)** drop-down to **Restrict**.

1. Select **Done (6)**.

    ![Referential Restrict relationship.](../media/pl200-p8t3p2.png)

1. In the **Objects** pane on the left, select **Columns** for the **Project** table.

1. Select the **Project Lead** column.

1. In the **Edit column** pane that appears on the right-hand side of the screen, expand **Advanced options** and scroll down.

1. Check the **Enable auditing** box.

1. Select **Save**.

## Exercise 4: Hierarchical relationship

In this exercise, you will create a new hierarchical relationship on the region table.

### Task 4.1: Create new hierarchical relationship

1. Navigate to the Power Apps Maker portal `https://make.powerapps.com`

1. Make sure you are in your **PL Development** environment.

1. Select **Solutions**.

1. Open the **Fabrikam Environmental** solution.

1. In the **Objects** pane on the left, expand **Tables**.

1. Select the **Region** table.

1. Select **+ New**, and then select **Relationship** and then select **+ One-to-many**.

1. In the **One-to-many** pane that appears on the right-hand side of the screen, select **Region** in the **Related (Many)** drop-down.

1. Enter `Parent Region` for **Lookup column display name**.

1. Enter `parentregionid` for **Lookup column name**.

1. Check the **Hierarchical** box.

1. Expand **General**.

1. Enter `parentregion_region` for **Relationship name**.

1. Expand **Advanced options**.

1. Change the **Delete** drop-down to **Restrict**.

1. Select **Done**.

## Exercise 5: Project Outcome relationships

In this exercise, you will create two many-to-one relationships for the Project Outcome table to the Project and Outcome tables. These relationships will be used to replace the many-to-many relationship between the Project and Outcome tables.

### Task 5.1: Create new relationship to Project

1. Navigate to the Power Apps Maker portal `https://make.powerapps.com`

1. Make sure you are in your **PL Development** environment.

1. Select **Solutions**.

1. Open the **Fabrikam Environmental** solution.

1. In the **Objects** pane on the left, expand **Tables**.

1. Select the **Project Outcome** table.

1. Under **Schema**, select **Relationships**.

1. Select **+ New relationship** and then select **Many-to-one**.

1. In the **Many-to-one** pane that appears on the right-hand side of the screen, select **Project (1)** in the **Related (One)** drop-down.

1. Enter `Project` for **Lookup column display name (2)**.

1. Enter `projectid` for **Lookup column name (3)**.

1. Expand **General**.

1. Enter `project_projectoutcome` for **Relationship name (4)**.

1. Expand **Advanced options**.

1. Change the **Type of behavior** drop-down to **Parental (5)**.

1. Select **Done (6)**.

    ![Cascade relationship.](../media/pl200-p8t5p1.png)

### Task 5.2: Create new relationship to Outcome

1. Select **+ New relationship** and then select **Many-to-one**.

1. In the **Many-to-one** pane that appears on the right-hand side of the screen, select **Outcome** in the **Related (One)** drop-down.

1. Enter `Outcome` for **Lookup column display name**.

1. Enter `outcomeid` for **Lookup column name**.

1. Expand **General**.

1. Enter `outcome_projectoutcome` for **Relationship name**.

1. Expand **Advanced options**.

1. Change the **Type of behavior** drop-down to **Parental**.

1. Select **Done**.

    > **Note:** An error will be shown saying that you cannot create another parental relation with the contoso_outcome table.

1. Change the **Type of behavior** drop-down to **Referential**.

1. Change the **Delete** drop-down to **Restrict**.

1. Select **Done**.

### Task 5.3: Set required and enable auditing on new lookup columns

1. In the **Objects** pane on the left, select **Columns** for the **Project Outcome** table.

1. Select the **Project** column.

1. In the **Edit column** pane that appears on the right-hand side of the screen, Change the **Required** drop-down to **Business required**.

1. Expand **Advanced options** and scroll down.

1. Check the **Enable auditing** box.

1. Select **Save**.

1. Select the **Outcome** column.

1. In the **Edit column** pane that appears on the right-hand side of the screen, change the **Required** drop-down to **Business required**.

1. Expand **Advanced options** and scroll down.

1. Check the **Enable auditing** box.

1. Select **Save**.

### Task 5.4: Mappings

1.  In the **Fabrikam Environmental** solution, select the **Objects** page and select **All**.

1.  Select the ellipsis menu **(...) (1)** and select **Switch to classic (2)**.

    ![Cascade relationship.](../media/pl200-p8t5p2.png)

1.  In the legacy **Solution Explorer**, expand **Entities**.

    ![Cascade relationship.](../media/pl200-p8t5p3.png)

1.  Expand **Project**.

1.  Select **1:N Relationships**.

1.  Select the relationship between **Project** and **Project Outcome**.

    ![One to many relationships in Solution Explorer.](../media/pl200-p8t5p4.png)

1.  Select **More Actions** and select **Edit** from the top menu bar.

1.  Select **Mappings (1)**.

1.  Select **New (2)**.

    ![One to many relationships in Solution Explorer.](../media/pl200-p8t5p5.png)

1.  In the left-hand side, select **contoso_projecttitle (1)**.

1.  In the right-hand side, select **contoso_title (2)**.

1.  Select **OK (3)**.

    ![One to many relationships in Solution Explorer.](../media/pl200-p8t5p6.png)

1.  Select **New**.

1.  In the left-hand side, select **contoso_projectsummary (1)**.

1.  In the right-hand side, select **contoso_comments (2)**.

1.  Select **OK (3)**.

    ![One to many relationships in Solution Explorer.](../media/pl200-p8t5p7.png)

1.  Select **Save and Close (1)**. Select **Publish All Customizations (2)**.

    ![One to many relationships in Solution Explorer.](../media/pl200-p8t5p9.png)

    ![One to many relationships in Solution Explorer.](../media/pl200-p8t5p8.png)

1.  Close the **Solutions Explorer** tab.

## Exercise 6: Connections

In this exercise, you will enable connections for the resource and milestone tables.

### Task 6.1: Enable connections on Resource

1. Navigate to the Power Apps Maker portal `https://make.powerapps.com`

1. Make sure you are in your **PL Development** environment.

1. Select **Solutions**.

1. Open the **Fabrikam Environmental** solution.

1. In the **Objects** pane on the left, expand **Tables**.

1. Select the **Resource** table.

1. Select **Properties**.

1. In the **Edit table** pane that appears on the right-hand side of the screen, expand **Advanced options** and scroll down.

1. Check the **Can have connections** box.

1. Select **Save**.

### Task 6.2: Enable connections on Milestone

1. Navigate to the Power Apps Maker portal `https://make.powerapps.com`

1. Make sure you are in your **Development** environment.

1. Select **Solutions**.

1. Open the **Fabrikam Environmental** solution.

1. In the **Objects** pane on the left, expand **Tables**.

1. Select the **Milestone** table.

1. Select **Properties**.

1. In the **Edit table** pane that appears on the right-hand side of the screen, expand **Advanced options** and scroll down.

1. Check the **Can have connections** box.

1. Select **Save**.

### Task 6.3: Publish changes

1. In the solution, select the **Overview (1)** page.
 
1. Select **Publish all customizations (2)**.
 
    ![Overview.](../media/pl200-p8t6p1.png)

### Task 6.4: Add connection roles

1. In the **Fabrikam Environmental** solution, select the **Objects** page and select **All**.

1. Select **+ New (1)** > **More (2)** and then select **Connection Role (3)**.

    ![Overview.](../media/pl200-p8t6p2.png)

1. Enter `Contributor` for **Name (1)**.

1. Select the **Only these record types (2)** radio button.

1. Select **Resource (3)**.

1. Select the **Save (4)** icon.

    ![Add connection role.](../media/pl200-p8t6p3.png)

1. Under **Matching connection roles**, select **New**.

    > **Note:** You may need to disable the pop-up blocker in your browser.

1. Enter `Contributed to` for **Name**.

1. Select the **Only these record types** radio button.

1. Select **Milestone**.

1. Select the **Save and Close** icon.

1. Select the **Save and Close** icon.

1. Select **Done**.

    ![Add connection role.](../media/pl200-p8t6p4.png)

1. Select **+ New** > **More** and then select **Connection Role**.

1. Enter `Advisor` for **Name**.

1. Select the **Only these record types** radio button.

1. Select **Resource**.

1. Select the **Save** icon.

1. Under **Matching connection roles**, select **Add Existing**.

1. Add **Contributed to (1)** to the **selected records** by selecting the row using the **Select (2)** button.

1. Select **Add (3)**.

   ![Add connection role.](../media/pl200-p8t6p5.png)

1. Select the **Save and Close** icon.

1. Select **Done**.

## Exercise 7: Calculated and rollup columns

In this exercise, you will use relationships to create calculated and rollup fields. The calculated column will add the email address for the approver to the outcome table. The rollup column will sum the funding values of projects.

### Task 7.1: Calculated column for a many-to-one relationship

1. Navigate to the Power Apps Maker portal `https://make.powerapps.com`

1. Make sure you are in your **PL Development** environment.

1. Select **Solutions**.

1. Open the **Fabrikam Environmental** solution.

1. In the **Objects** pane on the left, expand **Tables**.

1. Select the **Outcome** table.

1. Select **+ New** > **Column**.

1. Enter `Approver Email` for **Display Name**.

1. Enter `Email address for approver` for **Description**.

1. Select **Single line of text** in the **Data type** drop-down.

1. Select **Text** in the **Format** drop-down.

1. Change the **Behavior** drop-down to **Calculated**.

1. Select **Save and edit**.

    >Note: If the new window doesn't open, then go to the column **Approver Email** and then click on **Edit**.

    ![Add connection role.](../media/pl200-p8t7p1.png)

1. When the new browser window opens, select **+ Add condition**.

1. Select **Approver** for **Field**.

1. Select **Contains data** for **Operator**.

1. Select the green check mark.

    > NOTE: You may need to resize the window to see the check marks.

1. Select **+ Add Action**.

1. Enter the following formula:

    ```contoso_approveruserid.internalemailaddress```

    > NOTE: You can use intellisense to type and select the elements in the formula.

1. Select the blue check mark.

1. Select **SAVE AND CLOSE**.

    ![Add connection role.](../media/pl200-p8t7p2.png)

### Task 7.2: Rollup column for the project one-to-many relationship

1. In the **Objects** pane on the left, expand **Tables**.

1. Select the **Project** table.

1. Select **+ New** > **Column**.

1. Enter `Total Project Funding` for **Display Name**.

1. Select **Currency** in the **Data type** drop-down.

1. Change the **Behavior** drop-down to **Rollup**.

1. Select **Save and edit**.

1. When the new browser window opens, select **+ Add related entity**.

1. Select **Project Funding (Project)** for **Related**.

1. Select the blue check mark.

1. Select **+ Add condition**.

1. Choose **Status** for **Field**.

1. Choose **Equals** for **Operator**.

1. Verify **Active** is selected for **Value**.

1. Select the green check mark.

1. Select **+ Add aggregation**.

1. Select **SUM** for **Aggregate Function**.

1. Select **(Project Funding) Funding amount** for **Aggregate Related Entity Field**.

1. Select the green check mark.

1. Select **SAVE AND CLOSE**.

    ![Add connection role.](../media/pl200-p8t7p3.png)

### Task 7.3: Publish changes

1. In the solution, select the **Overview** page.
   
   ![Overview.](../media/15-1.png)


1. Select **Publish all customizations**.

## Exercise 8: Solutions

In this exercise, you will export the solution from the Development environment and import it into the Live environment.

### Task 8.1: Solution checker

1. Navigate to the Power Apps Maker portal `https://make.powerapps.com`

1. Make sure you are in the **PL Development** environment.

1. Select **Solutions (1)**.

1. Select the **Fabrikam Environmental (2)** solution row but do not open it.

1. Select **Solution checker (3)** > **Run (4)**.

    ![Add connection role.](../media/pl200-p8t8p1.png)

1. Wait a few minutes for the solution checker to complete.

    >**Note:** If if the checker is still running after 15 minutes, try refreshing the tab.

1. Select **Solution checker** > **View results**.

1. You should see several warnings for the canvas app in the solution.

    ![Add connection role.](../media/pl200-p8t8p2.png)

1. Select the **back arrow** to return to solutions.

### Task 8.2: Export managed solution

1. Select the **Fabrikam Environmental** solution row but do not open it.

1. Select **Export solution**.

1. Select **Next**.

1. The version number should have been incremented to **1.1.11.4**.

1. Change the version number to `1.1.11.6` **(1)**.

1. Select **Managed (2)** for **Export As**.

1. Select **Export (3)**.

    ![Add connection role.](../media/pl200-p8t8p3.png)

1. The export will be prepared in the background. When the solution is ready, select the **Download** button.

    ![Add connection role.](../media/pl200-p8t8p4.png)

### Task 8.3: Export unmanaged solution

1. Select the **Fabrikam Environmental** solution row but do not open it.

1. Select **Export Solution**.

1. Select **Next**.

1. The version number should have been incremented to **1.1.11.7**.

1. Change the version number to `1.1.11.6`.

1. Select **Unmanaged** for **Export As**.

1. Select **Export**.

1. The export will be prepared in the background, when the solution is ready click the **Download** button.


### Task 8.4: Import managed solution

1. Switch environments by using the Environment Selector in the upper right corner of the Maker portal.

1. Select the **PL Live** environment from the list.

1. Select **Solutions (1)**.

1. Select **Import solution (2)**.

    ![Add connection role.](../media/pl200-p8t8p6.png)

1. Select **Browse**, change to the **Downloads** folder and select **FabrikamEnvironmental_1_1_11_6_managed.zip** and select **Open**.

1. Select **Next**.

1. Select **Next**.

    You need to create connections for the solution.

1. Both connections should be selected.

1. Select **Next**.

1. Select **Import**. The solution will import in the background.

    ![Add connection role.](../media/pl200-p8t8p7.png)


## Challenge (Optional)

Under **Processes**, examine the classic workflow **Project Funding Name.**

Create a new workflow that meets the following requirements: 
- Sets the **Title** column on the Project Outcome table when a new record is created or when a project or an outcome lookup column is changed.
- Sets the column to a concatenation based on the relationships you configured in this lab (see examples in the Project Funding Name and Project Resource Name workflows). 

### Review
In this lab, you have changed relationship behaviours, added new relationship, created new hierarichial and project outcome relationships, enabled connections, created calculated and rollup fields, exported and imported solutions.

![](../media/pl200-gs-nextpage.png)