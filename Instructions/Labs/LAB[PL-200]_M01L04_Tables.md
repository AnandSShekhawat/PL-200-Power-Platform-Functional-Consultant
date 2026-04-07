# Lab 1.4: Tables

## Scenario

You are a Power Platform functional consultant and have been assigned to the Fabrikam project for the next stage of the project.

You need to familiarize yourself with the data model and then make changes to tables and their properties for this phase of the project.

![](../media/pl200-p6t1p1.png)

In this practice lab, you will be modifying table properties and creating a new custom table.

## Lab objectives
In this lab, you will perform:

+ Exercise 1: Explore the data model 
+ Exercise 2: Change table properties
+ Exercise 3: Create a custom table
  
## Exercise 1: Explore the data model

In this exercise, you will be examining the tables in the Fabrikam Environmental solution. Take some time to familiarize yourself with your client, Fabrikam's, data model and existing business rules. 


### Task 1.1: Examine tables

1.  Navigate to the Power Apps Maker portal `https://make.powerapps.com`

1.  Make sure you are in your **PL Development** environment.

1.  Select **Solutions** from the left navigation pane.

1.  Open the **Fabrikam Environmental** solution.

1.  In the **Objects** pane on the left, expand **Tables**.

1.  Select the **Project** table.

    ![Project table.](../media/pl200-p6t1p2.png)

1.  Under **Schema**, select **Columns**. You will see columns including **Project Title, Project Type, Estimated End, and Program**.

1.  In the **Objects** pane on the left, select **Relationships**. You will see multiple One-to-many, Many-to-one, and a many-to-many relationships.

    ![Project table.](../media/pl200-p6t1p3.png)

1.  Expand the **Milestone** table and examine its columns and relationships.

    ![Project table.](../media/pl200-p6t1p4.png)

1.  Expand the **Project Funding** table and examine its columns and relationships.

1.  Select **Business rules (1)** under the **Project Funding** table. There is a rule for the funding percentage **(2)**. Open the business rule and examine how it works. 

    ![Project table.](../media/pl200-p6t1p5.png)

    ![Project table.](../media/pl200-p6t1p6.png)

1.  Close the business rule and select **Done**. 

1.  Expand the **Project Resource** table and examine its columns and relationships.

## Exercise 2: Change table properties

In this exercise, you will be updating the properties on the Project table to allow users to add attachments and use activities with project records. You will also enable audit and other search on other tables in the solution.


### Task 2.1: Enable attachments and activities on the project table

1.  Navigate to the Power Apps Maker portal `https://make.powerapps.com`

1.  Make sure you are in the **PL Development** environment.

1.  Select **Solutions**.

1.  Open the **Fabrikam Environmental** solution.

1.  In the **Objects** pane on the left, expand **Tables**.

1.  Select the **Project** table.

1.  Select **Properties**.

    ![Project table.](../media/pl200-p6t2p1.png)

    > **Note:** If Properties is not shown, maximize your browser and/or zoom in until Properties appears.

1.  In the **Edit table** pane that appears on the right-hand side of the screen, check the **Enable attachments (including notes and files) (1)** box.

    ![Project table.](../media/pl200-p6t2p2.png)

1.  Expand **Advanced options (2)** and scroll down.

1.  Check the **Creating a new activity (1)** box.

1.  Select **Save (2)**.

     ![Project table.](../media/pl200-p6t2p3.png)

### Task 2.2: Enable audit and search on the Milestone table

1.  Select the **Milestone** table.

1.  Select **Properties**.

1.  In the **Edit table** pane that appears on the right-hand side of the screen, expand **Advanced options** and scroll down.

1.  Check the **Audit changes to its data (1)** box.

1.  Check the **Appear in search results (2)** box.

1.  Select **Save (3)**.

    ![Project table.](../media/pl200-p6t2p4.png)


### Task 2.3: Enable audit on the Outcome table

1.  Select the **Outcome** table.

1.  Select **Properties**.

1.  In the **Edit table** pane that appears on the right-hand side of the screen, expand **Advanced options** and scroll down.

1.  Check the **Audit changes to its data (1)** box.

1.  Select **Save (2)**.

    ![Project table.](../media/pl200-p6t2p5.png)


### Task 2.4: Enable audit on the Project Funding table

1.  Select the **Project Funding** table.

1.  Select **Properties**.

1.  In the **Edit table** pane that appears on the right-hand side of the screen, expand **Advanced options** and scroll down.

1.  Check the **Audit changes to its data** box.

1.  Select **Save**.


## Exercise 3: Create a custom table

In this exercise, you will be creating a new custom table named Project Outcome. This table will link outcomes to projects. Currently there is a many-to-many relationship between Project and Outcome. This table will be used in place of this relationship.

In later labs you will be adding columns and relationships to this custom table.


### Task 3.1: Create custom table

1.  In the **Objects** pane on the left, select **Tables (1)**.

1.  Select the **+ New (2)** drop-down and select **Table (3)** then click on **Tables (advanced properties) (4)**.

    ![Project table properties.](../media/pl200-p6t3p1.png)

1.  Enter `Project Outcome` for **Display Name (1)**. The plural name will be automatically populated.

1.  Enter `Environmental outcomes for a project` for **Description (2)**.

1.  Expand **Advanced options (3)**.

    ![Project table properties.](../media/pl200-p6t3p2.png)

1.  Uncheck the **Apply duplicate detection rules** box.

1.  Uncheck the **Doing a mail merge** box.

1.  Check the **Audit changes to its data** box.

1.  Scroll up, and select the **Primary column (1)** tab.

1.  Enter `Title` for **Display Name (2)**.

1.  Expand **Advanced options (3)**.

    ![Project table properties.](../media/pl200-p6t3p3.png)

1.  Change the **Column requirement (1)** drop-down to **Optional**.

1.  Change the **Maximum character count (2)** to **200**.

1.  Select **Save (3)**.

    ![Project table properties.](../media/pl200-p6t3p4.png)
   

### Task 3.2: Publish changes

1.  In the solution select the **Overview (1)** page.

1.  Select **Publish all customizations (2)**.

    ![Project table properties.](../media/pl200-p6t3p5.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
>
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help.
 
<validation step="3e94c9bf-2e05-4ddd-bc9f-2d3a6584db1e" />

## Review
In this lab, you explored the existing data model, reviewed tables, relationships, and business rules. You updated table properties to enable features like attachments, activities, auditing, and search, and created a new custom table to enhance data structure and support future relationships. Great work!


![](../media/pl200-gs-nextpage.png)
