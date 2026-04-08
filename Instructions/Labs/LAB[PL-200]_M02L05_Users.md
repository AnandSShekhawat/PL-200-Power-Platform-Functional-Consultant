# Lab 2.2: Users and Teams

## Scenario

You are a Power Platform functional consultant and have been assigned to the Fabrikam project for the next stage of the project.

In this practice lab, you will be adding users and assigning security roles.

You will create a Team and adding users to the Team.

You will add the users and team to column security profiles.

> IMPORTANT: These labs are designed for use with a Microsoft 365 tenant provisioned with Microsoft 365 licenses and users. If you are not using an Authorized Lab Hoster (ALH) lab environment, you will need to create the users in Microsoft 365.

## Lab objectives
In this lab, you will:

+ Exercise 1: Assign License to the users
+ Exercise 2: Add users to your environment
+ Exercise 3: Create a team
+ Exercise 4: Column security profile

## Exercise 1: Assign License to the users

In this exercise, you'll assign license to the following user through the Microsoft 365 admin center.

### Task 1.1: Assign license to users

1. Navigate to the Microsoft 365 admin center using the following URL: `https://admin.cloud.microsoft`

1. If prompted, sign in using the following credentials:

    - **Email/Username:** <inject key="AzureAdUserEmail"></inject>

    - **Password:** <inject key="AzureAdUserPassword"></inject>

1. From the left navigation pane, select **Users (1)** and then select **Active users (2)**.

    ![](../media/pl200-p2t2p1.png)

1. From the list of Active users, select **Alex Wilber (1)**. In the **Alex Wilber** pane on the right, select the **Licenses and apps (2)** tab and then check the box next to **Microsoft Power Apps for Developer (3)** and then select **Save changes (4)**. 

    ![](../media/pl200-p2t2p2.png)

1. Now close the pane using the **X** icon on the top right.

    ![](../media/pl200-p2t2p3.png)

1. Now perform the **step 3 and 4** for the following users as well to assign them **Microsoft Power Apps for Developer** license :

    - **Megan Brown**
    - **Patti Fernandez**

## Exercise 2: Add users to your environment

### Task 2.1: Create Users

1. Navigate to the Power Platform admin center `https://aka.ms/ppac`

1. Select **Manage** and then **Environments** from the left navigation pane.

1. Select the **PL Development** environment.

1. Select **Settings**.

    ![](../media/pl200-p11t1p1.png)

1. Expand **Users + permissions (1)**.

1. Select **Users (2)**.

    ![](../media/pl200-p11t1p2.png)

1. Select **+ Add user**.

    ![](../media/pl200-p11t1p3.png)

1. Enter `Alex` in **Enter a name or an email address** and select **Alex Wilber (1)**.

1. Select **Add (2)**.

    ![](../media/pl200-p11t1p4.png)

1. Select the **Environmental User (1)** role.

1. Select **Save (2)**.

    ![](../media/pl200-p11t1p5.png)

1. Select **Save** on Role assignement confirmation popup.

    ![](../media/pl200-p11t1p6.png)

1. Select **+ Add user**.

1. Enter `Megan` in **Enter a name or an email address** and select **Megan Bowen**.

1. Select **Add**.

1. Select the **Environmental User** and **Environmental Manager** roles.

1. Select **Save**.

1. Select **Save** on Role assignement confirmation popup.

1. Select **+ Add user**.

1. Enter `Patti` in **Enter a name or an email address** and select **Patti Fernandez**.

1. Select **Add**.

1. Select the **Environmental User** and **Environmental Administrator** roles.

1. Select **Save**.

1. Select **Refresh** to view the updated list of users.

    ![](../media/pl200-p11t1p8.png)

## Exercise 3: Create a team

### Task 3.1: Create Team

1. Navigate to the Power Platform admin center `https://aka.ms/ppac`

1. Select **Environments** from the left navigation pane.

1. Select the **PL Development** environment.

1. Select **Settings**.

1. Expand **Users + permissions**.

1. Select **Teams**.

    ![](../media/pl200-p11t2p1.png)

1. Select **+ Create team**.

    ![](../media/pl200-p11t2p2.png)

1. Enter `Fabrikam Managers`**(1)** for **Team name**.

1. Enter `org` and select the root business unit **(2)**.

1. Enter `ODL_user` in **Administrator** and select **ODL_User<inject key="DeploymentID"></inject> (3)**.

1. Select **Owner** **(4)** in the **Team type** drop-down.

1. Select **Next (5)**.

    ![](../media/pl200-p11t2p3.png)

1. Enter `Megan` in **Enter a name or an email address** and select **Megan Bowen (1)**.

1. Select **Next (2)**.

    ![](../media/pl200-p11t2p4.png)

1. Select the **Environmental User** and **Environmental Manager** roles.

1. Select **Save**.

1. Select **Save** on Role assignement confirmation popup.

    ![](../media/pl200-p11t2p5.png)

## Exercise 4: Column security profile

### Task 4.1: Add user to column security profile

1. Navigate to the Power Platform admin center `https://admin.powerplatform.microsoft.com`

1. Select **Manage** and then **Environments** from the left navigation pane.

1. Select the **PL Development** environment.

1. Select **Settings**.

1. Expand **Users + permissions**.

1. Select **Column security profiles**.

    ![](../media/pl200-p11t3p1.png)

1. Select **Outcome Approval Read-Only**.

    ![](../media/pl200-p11t3p2.png)

1. Select the **Users (1)** tab.

1. Select **+ Add Users (2)**.

    ![](../media/pl200-p11t3p3.png)

1. Enter `Alex` in **Enter a name or an email address** and select **Alex Wilber**.

1. Select **Add**.


### Task 4.2: Add team to column security profile

1. Select **Column Security Profiles** in the breadcrumb at the top of the screen.

    ![](../media/pl200-p11t3p4.png)

1. Select **Outcome Approval**.

1. Select the **Users** tab.

1. Select **+ Add Users**.

1. Enter `Patti` in **Enter a name or an email address** and select **Patti Fernandez**.

1. Select **Add**.

1. Select the **Teams** tab.

    ![](../media/pl200-p11t3p5.png)

1. Select **+ Add Teams**.

1. Enter `Fabrikam` in **Search for a team by team name** and select **Fabrikam Managers**.

1. Select **Add**.

    ![](../media/pl200-p11t3p6.png)

## Review
In this lab, you assigned license to the users, added users to the environment and assigned appropriate security roles. You created a team, added members, and assigned roles to the team. Additionally, you configured column security profiles by assigning users and teams to control access to sensitive data. Great work!

### You have successfully completed the lab. Click on Next >> to proceed with the next lab.

![](../media/pl200-gs-nextpage.png)
