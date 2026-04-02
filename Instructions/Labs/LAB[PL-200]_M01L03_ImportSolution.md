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
- Classic workflows
- Model-driven apps
- Charts and dashboards
- Canvas app
- Cloud flows
- Business process flows
- Power Virtual Agents chatbot

In this lab, you will import the developed solutions and data.

## Lab objectives
In this lab, you will perform:

+ Exercise 1: Import Fabrikam solutions
+ Exercise 2: Import data
+ Exercise 3: Sign up for Power Pages

## Exercise 1 - Import Fabrikam solutions

In this exercise, you will import the main solution into the **Development** environment.

### Task 1.1 – Main solution

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

## Task 1.2 - Set preferred solution

1.  Navigate to `https://make.powerapps.com`

1. Make sure you are in the **PL Development** environment.

1. Select **Solutions (1)** and select **Manage (2)** in the Current preferred solution tile.

     ![](../media/pl200-p5t1p12.png)

1. Select **Fabrikam Environmental (contoso) (1)** and click **Apply (2)**.

     ![](../media/pl200-p5t1p13.png)

## Exercise 2 - Import data

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

### Task 2.2 - Import data with the Configuration Migration Tool

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

### Task 2.3 – Load Outcome Excel file to OneDrive

1.  Navigate to the Power Apps Maker portal `https://make.powerapps.com`

1.  Select the **Waffle** button in the upper left corner to change applications and select **OneDrive**. (It may take a moment for your OneDrive to be set up. Select **Your OneDrive is ready** when you see it on the screen.)

1.  Select **+ Create or upload** and select **Files upload**.

1.  Locate and select the **Outcome data.xlsx** file and select **Open**.

    > **Note:** This file should be located in the Documents\PL-200 folder on your machine.


1.  For the Approvals connection, in the **Select a connection** drop-down, choose **+ New connection**.

     ![](../media/exerc1(5).png)
    
1.  A new tab will open in the browser. Select **Create**.

     ![](../media/ex1(6).png)

1.  Switch back to the tab where you are importing the solution and select **Refresh**.

     ![](../media/ex1(7).png)

1.  For the Microsoft Dataverse connection, in the **Select a connection** drop-down, choose **+ New connection**.

1.  A new tab will open in the browser. Select **Create**. If prompted, sign in with your Microsoft 365 credentials.

1.  Switch back to the tab where you are importing the solution and select **Refresh**.

1.  Both connections should now be configured. Select **Import**.

     ![](../media/ex1(8).png)
    
1. The solution will import in the background. This may take a few minutes.

    > **Alert:** Wait until the solution has finished importing before continuing to the next step.

1.  When the solution has imported successfully, open the **Fabrikam Environmental** solution.

     ![](../media/ex1(9).png)

1.  In the solution, select the **Overview** page. Select **Publish all customizations**. 

     ![](../media/ex1(10).png)

### Task 1.2 – Power Virtual Agents solution

1.  Navigate to `https://make.powerapps.com`

1.  Make sure you are in your **Development** environment.

     ![](../media/ex1(1).png)

1.  Select **Solutions**.

1.  Select **Import solution**.

1.  Select **Browse**, locate the **FabrikamChatbot_1_1_1_1.zip** file and select **Open**.

    > **Note:** This file is located in the C:\Allfiles\Labs folder on your machine.

1.  Select **Next**.

     ![](../media/ex1(11).png)

1.  Select **Import**. The solution will import in the background.

## Exercise 2 - Import data

In this exercise, you will import data the into the **Development** environment using the Configuration Migration Tool.


### Task 2.1 - Import data

1.  In your lab virtual machine, open **File Explorer**.

1.  Navigate to **C:\Allfiles\Labs\ConfigurationMigration**.

1.  Double-click on **DataMigrationUtility**
   
1.  Choose **Import data**. Select **Continue**.

     ![](../media/ex2(1).png)

1.  Select **Office 365** for **Deployment Type**.

1.  Check the **Display list of available organizations** box.

1.  Enter your Microsoft 365 tenant credentials and  select **Login**.

     ![](../media/ex2(2).png)

1.  Choose your **Development** environment.

1.  Select **Login**.

     ![](../media/ex2(3).png)

1.  Select the ellipses (...) and locate and select **Fabrikam Environment data.zip** file.

    > **Note:** This file is located in the C\AllFiles\Labs folder on your machine.

1.  Select **Open**. The data file will be validated.

1.  Select **Import Data**. The import process will take approximately a minute.

     ![](../media/ex2(4).png)

1.  Select **Exit**.

1.  Select the **X** to close the Configuration Migration Tool.


## Exercise 3 - Sign up for Power Pages

In this exercise, you will provision a Power Pages site. This can take a while, so you will follow these steps to start the provisioning process in the background while you progress through your labs. You will configure the site in a future lab.

### Task 3.1 - Create a Power Pages site

1.  Navigate to the Power Pages portal `https://make.powerpages.microsoft.com/` and sign in with your Microsoft 365 credentials if prompted.

1.  Use the Environment selector to switch to your **Development** environment.

     ![](../media/ex3(1).png)

1.  Select **Get started**.

1.  If you are asked about your experience creating websites, select **Skip**.

1.  Choose the default design template, **Starter layout 1**, and select **Choose this template**.

     ![](../media/ex3(2).png)   

1.  Enter `Fabrikam Milestones` for **Give your site a name**.

1.  Use the autogenerated web address.

     ![](../media/ex3(3).png)

1.  Select **Done**.

    > The portal site will deploy. It can take around an hour for your site to fully deploy.

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Navigate to the Lab Validation Page, from the upper right corner in the lab guide section.
- Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

### Review
In this lab, you imported Fabrikam solutions, imported data and signed up for power pages.
