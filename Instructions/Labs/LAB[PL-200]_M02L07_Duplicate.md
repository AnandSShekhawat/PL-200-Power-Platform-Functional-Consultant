# Lab: Duplicate detection (Optional)

## Scenario

You are a Power Platform functional consultant and have been assigned to the Fabrikam project for the next stage of the project.

In this practice lab, you will implement duplicate detection rules so that duplicate projects cannot be created for the same program.

## Lab objectives
In this lab, you will perform:

+ Task 1: Create duplicate detection rule
  
## Exercise 1: Create new duplicate detection rule

In this exercise, you will create a new duplicate detection rule that will mark a Project as duplicate if it has the same project title and program.

### Task 1.1: Create duplicate detection rule

1. Navigate to the Power Platform admin center `https://admin.powerplatform.microsoft.com`.

1. Select **Environments** from the left navigation pane.

1. Select the **PL Development** environment.

1. Select **Settings**.

1. Expand **Data management (1)**.

1. Select **Duplicate detection rules (2)**.

    ![](../media/pl200-p13t1p1.png)

1. Select **New**.

    ![](../media/pl200-p13t1p2.png)

1. Enter `Duplicate project` **(1)** for **Name**.

1. Select **Project** for both **Base Record Type** **(2)** and **Matching Record Type** **(3)**.

1. Check the **Exclude inactive matching records (4)**  box.

1. Under **Field**, select **Project Title (5)**.

1. Select **Exact Match** for **Criteria (6)**.

1. Check the **Ignore Blank Values (7)** box.

1. Add another field, select **Program (8)**.

1. Select **Exact Match** for **Criteria (9)**.

1. Check the **Ignore Blank Values (10)** box.

1. Select **Save (11)**.

    ![](../media/pl200-p13t1p3.png)

1. Select **Publish**.

1. Select **OK**.

1. Select **Close**.

## Review
In this lab, you created and configured a duplicate detection rule in Microsoft Dataverse to prevent duplicate project records based on project title and program. You defined matching criteria, enabled the rule, and published it to ensure data consistency and integrity. Great work!

### You've successfully completed the Hand's-on lab!

