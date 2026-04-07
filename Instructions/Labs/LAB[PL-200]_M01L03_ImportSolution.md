# Lab 1.3: Import solution

## Scenario

Fabrikam is an environmental consultancy that advises customers on programs and related projects covering water, air, and soil.

Fabrikam works long-term with its customers to improve the sustainability of natural resources. A Power Platform solution has been built by Contoso for Fabrikam to support the delivery of programs and projects.

You are a Power Platform functional consultant and have been assigned to the Fabrikam project for the next stage of the project.

You need to prepare your development environment by importing solutions and data.

The solutions contain:

- Microsoft Dataverse data model
- Security roles
- Business rules
- Dataverse classic workflows
- Model-driven apps
- Charts and dashboards
- Canvas app
- Power Automate cloud flows
- Business process flows

In this lab, you will import the developed solutions and data.

## Lab objectives
In this lab, you will perform:

+ Exercise 1: Import Fabrikam solutions
+ Exercise 2: Import data

## Exercise 1: Import Fabrikam solutions

In this exercise, you will import the main solution into the **Development** environment.

### Task 1.1: Main solution

1.  Navigate to `https://make.powerapps.com`

1.  Click on **Environment (1)** from the top right corner and make sure you are in your **PL Development (2)** environment.

     ![](../media/pl200-p5t1p1.png)
    
1.  Select **Solutions (1)** and then select **Import solution (2)**.

     ![](../media/pl200-p5t1p2.png)

1.  Select **Browse (1)** and in the Open window navigate to `C:\Allfiles\Labs` **(2)** and locate the **FabrikamEnvironmental_1_1_11_3.zip (3)** file and select **Open (4)**. Select **Next (5)**.

     ![](../media/pl200-p5t1p3.png)

     ![](../media/pl200-p5t1p4.png)

 1.  Select **Next** again.

     ![](../media/pl200-p5t1p5.png)

1. Wait while connections are created and select **Next**.

     ![](../media/pl200-p5t1p6.png)

1. Select **Import**. The solution will import in the background. This may take a few minutes.

     ![](../media/pl200-p5t1p7.png)

     ![](../media/pl200-p5t1p8.png)

     >**Note:** Wait until the solution has finished importing before continuing to the next step.

1. When the solution has imported successfully, open the **Fabrikam Environmental** solution.

     ![](../media/pl200-p5t1p9.png)

1. In the solution, select the **Overview** page.

     ![](../media/pl200-p5t1p10.png)

1. Select **Publish all customizations**.

     ![](../media/pl200-p5t1p11.png)

## Task 1.2: Set preferred solution

1.  Navigate to `https://make.powerapps.com`

1. Make sure you are in the **PL Development** environment.

1. Select **Solutions (1)** and select **Manage (2)** in the Current preferred solution tile.

     ![](../media/pl200-p5t1p12.png)

1. Select **Fabrikam Environmental (contoso) (1)** and click **Apply (2)**.

     ![](../media/pl200-p5t1p13.png)

## Exercise 2: Import data

In this exercise, you will import data the into the **PL Environment** environment using the Configuration Migration Tool and import Outcome rows into your Microsoft Dataverse environment using a dataflow.

### Task 2.1: Download and install Power Platform CLI

1.  Download the Power Platform CLI from `https://aka.ms/PowerAppsCLI`, then from the browser’s **Downloads** section select **Open file** for **powerapps-cli-1.0.msi** to start the installation.

     ![](../media/pl200-p5t2p1.png)

1.  In the setup wizard, accept the license agreement **(1)**, click **Install (2)**, and follow the prompts to complete the installation, then select **Finish**.

     ![](../media/pl200-p5t2p2.png)

1. Use the Start menu search to type **Command Prompt (1)**, then select **Command Prompt (2)** to open it. 

     ![](../media/pl200-p5t2p3.png)

1. Verify Power Apps CLI is installed by running the following command:

    ```
    pac install latest
    ```

    ![](../media/pl200-p5t2p4.png)

### Task 2.2: Import data with the Configuration Migration Tool

1. Open the **AzureCreds (1)** file from the desktop and note the **username and password (2)**, as you will need them in the subsequent steps.

     ![](../media/pl200-p5t2p6(1).png)

     ![](../media/pl200-p5t2p6(2).png)

1.  In the Command prompt, launch the **Configuration Migration Tool** using the following command:

    ```
    pac tool cmt
    ``` 

1.  Select **Import data (1)** and the select **Continue (2)**.

     ![](../media/pl200-p5t2p5.png)

1. Configure the login settings as follows:

     * Select **Office 365 (1)** for *Deployment Type*.
     * Check **Display list of available organizations (2)**.
     * Check **Show Advanced (3)**.
     * Select **Don't know (4)** for *Online Region*.
     * **Enter your credentials**: Paste the credentials from the **AzureCreds** file on the desktop
     * Select **Login (7)**.
     
          ![](../media/pl200-p5t2p6.png)

1.  Choose the **PL Development (1)** environment and then select **Login (2)**.

     ![](../media/pl200-p5t2p7.png)

1.  Select the **ellipsis (...) (1)**, navigate to `C:\AllFiles\Labs` **(2)**, choose the **Fabrikam Environment data (3)** zip file, and click **Open (4)**.

     ![](../media/pl200-p5t2p8.png)

1. The data file will be validated. Select **Import Data**. The import process will take approximately a minute.

     ![](../media/pl200-p5t2p9.png)

1.  Select **Exit**.

     ![](../media/pl200-p5t2p10.png)

1.  Select the **X** to close the Configuration Migration Tool.

### Task 2.3: Load Outcome Excel file to OneDrive

1.  Navigate to the Power Apps Maker portal `https://make.powerapps.com`

1.  Select the **Waffle (1)** button in the upper left corner to change applications and select **OneDrive (2)**. (It may take a moment for your OneDrive to be set up. Select **Your OneDrive is ready** when you see it on the screen.)

     ![](../media/pl200-p5t2p11.png)

1.  It will open in a new tab in the browser, select **+ Create or upload (1)** and select **Files upload (2)**.

1.  Navigate to `C:\Allfiles\Labs` **(3)** and select the **Outcome data.xlsx (4)** file and select **Open (5)**.
     
     ![](../media/pl200-p5t2p11(1).png)
     
     ![](../media/pl200-p5t2p12.png)

### Task 2.4: Create a dataflow to import Outcomes

1.  Navigate to the Power Apps Maker portal `https://make.powerapps.com`

1.  Make sure you are in the **PL Development** environment.

1.  Select **Tables (1)** from the left navigation menu.

1.  Select **Import (2)** from the action menu, then select **Import data with Dataflows (3)**, and then select **Excel workbook (4)** as the source.

     ![](../media/pl200-p5t2p13.png)

     ![](../media/pl200-p5t2p14.png)

1.  Select **Browse OneDrive...**, if prompted, sign in with your Microsoft 365 credentials.

     ![](../media/pl200-p5t2p15.png)

1.  Select the **Outcome data.xlsx (1)** file and then select **Select (2)**.

     ![](../media/pl200-p5t2p17.png)

1.  Select **Next**.

1.  Check the box next to **Table1 (1)**.

1.  Select **Next (2)**. Do not navigate away from this page.

     ![](../media/pl200-p5t2p16.png)

1.  Select the first three **Do Not Modify** columns. 

     >**Note:** You can hold **Ctrl** on the keyboard and click with the mouse to select multiple columns.

1.  On the **Home (1)** tab of the ribbon, use the **carrot icon (2)** at the far right side of the ribbon to expand the Home tab buttons. Select **Remove columns (3)** drop-down and select **Remove columns (4)** to remove these three columns.

     ![](../media/pl200-p5t2p18.png)

1.  Select the **Estimated Completion Date** column.

1.  Right-click on the **Estimated Completion Date (1)** column and select **Replace values... (2)**.

     ![](../media/pl200-p5t2p19.png)

1.  Enter `null` for **Value to find (1)**.

1.  For **Replace with (2)**, enter a date in three months time. Use date format **MM/DD/YYYY**.

1.  Select **OK (3)**. The Estimated Completion Dates should show the date chosen.

     ![](../media/pl200-p5t2p20.png)

1.  Select **Next**.

1.  Select **Load to existing table (1)**.

1.  Select **contoso_outcome (2)** from the **Destination table** drop-down.

     ![](../media/pl200-p5t2p21.png)

1.  Expand **Column mapping (3)** and check if **Estimated Completion Date**, **Goal**, **Outcome Description**, **Outcome Title**, and **Target Aim** are mapped **(4)** to their corresponding destination columns.

1.  Select **Next (5)**.

     ![](../media/pl200-p5t2p22.png)

1.  Select **Refresh manually**.

1.  Select **Publish**.

### Task 2.5: Test Your work

1.  Navigate to the Power Apps Maker portal `https://make.powerapps.com`

1.  Select **Tables**.

1.  Locate and open the **Outcome** table.

1.  You should see all the imported **Outcome** rows.

1.  In the Maker portal, select **Apps (1)** from the left navigation.

1.  For the **Environmental Project Delivery** model-driven app, select the ellipsis **(...) (2)** and select **Play (3)**, signing in with your Microsoft 365 credentials if prompted.

     ![](../media/pl200-p5t2p23.png)

1.  In the left navigation of the app, select **Outcomes**.

1.  The imported **Outcome** records should be in the view.

     ![](../media/pl200-p5t2p24.png)

     >**Note:** Records make take upto 10-15mins to reflect. 

1.  Select the title to open one of the imported **Outcome** records.

1.  Verify the **Estimated Completion Date** column is set to the future date.

1.  Verify the **Outcome Lifecycle** business process flow is visible at the top of the form.

## Review
In this lab, you prepared the development environment by importing solutions and data into Dataverse. You configured the preferred solution, used the Configuration Migration Tool and dataflows to load data, and validated the setup by reviewing records in the model-driven app. Great work!

![](../media/pl200-gs-nextpage.png)