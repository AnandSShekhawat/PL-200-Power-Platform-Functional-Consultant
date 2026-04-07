# Lab 3.3: Command bar

## Scenario

You are a Power Platform functional consultant and have been assigned to the Fabrikam project for the next stage of the project.

In this practice lab, you will be modifying the forms for the Fabrikam Environment model-driven apps.

You will be adding a command button to the project outcome form in the Environental Project Delivery app.

## Lab objectives

In this lab, you will perform:

- Exercise 1: Add command button

## Exercise 1: Add command button

In this exercise, you will configure the default form for the Project Outcome table.

### Task 1.1: Add command button to main form

In this task, you will perform the following changes to the Project Outcome form:

- add a command button to Project Outcomes in the app designer

1. Navigate to the Power Apps Maker portal `https://make.powerapps.com`

1. Make sure you are in the **PL Development** environment.

1. Select **Solutions**.

1. Open the **Fabrikam Environmental** solution.

1. In the **Objects** pane on the left, select  **Apps**.

1. Select the **Environmental Project Delivery** app, select the **Commands** menu **(⋮)**, and select **Edit** > **Edit in new tab**.

1. Select the **Pages** tab, Hover over **Project Outcome views** and select the ellipsis **(...) (1)** button.

1. Select **Edit command bar (2)** and select **Edit in new tab (3)**.

    ![](../media/pl200-p17t1p1.png)

1. Select **Main form (1)** and then select **Edit (2)**.

    ![](../media/pl200-p17t1p2.png)

1. Select **+ New (1)** and then select **Command (2)**.

    ![](../media/pl200-p17t1p3.png)

1. Select **Power Fx** and then select **Continue**.

1. Configure command bar button

   - Enter `Complete` for **Label (1)**.

   - Select **Use Icon (2)** for **Icon** and then select the **Accept (3)** icon.

   - Select **Run formula (4)** for **Action**.

   - Select **Open formula bar (5)**.

   - Replace the existing formula with following **(6)**:

    ```powerappsfl
    Patch('Project Outcomes', Self.Selected.Item, {'Outcome Completed Date': Now()})
    ```

   - Enter `Project Outcome complete` for **Tooltip title (7)**.

   - Enter `Set Outcome completed date` for **Tooltip description (8)**.

        ![](../media/pl200-p17t1p5.png)

        ![](../media/pl200-p17t1p6.png)

1. Select **Save and Publish (9)**.

1. **Close** the Command bar editor.
   
1.  In the **Environmental Project Delivery** app, select **Save and publish.**

1. **Close** the app designer.

## Review

In this lab, you customized the command bar of a model-driven app by adding a new button to the Project Outcome form. You configured the button using Power Fx to update records dynamically and enhanced user interaction with custom labels, icons, and tooltips. Great work!

### You have successfully completed the lab. Click on Next >> to proceed with the next lab.

![](../media/pl200-gs-nextpage.png)