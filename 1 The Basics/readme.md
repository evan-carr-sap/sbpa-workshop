
# SPA Workshop : The basics

## Table of Contents
- [Description](#section1)
- [Overview](#section2)
- [Requirements](#section3)
- [Create Business Process Project](#section4)
- [Create Business Process](#section5)
- [Create Trigger Form](#section6)
- [License](#licence)

## 1. Description <a name="section1"></a>

**SAP Build Process Automation aka SPBA** enables business users and technologists to become citizen developers. With powerful yet intuitive low-code and no-code capabilities, the solution supports you in driving automation by tapping into the expertise of citizen developers. It combines capabilities from SAP Workflow Management and SAP Intelligent RPA with a powerful, yet intuitive no-code development experience. The solution offers the following key features:
   
   - Build processes with an intuitive graphical interface
   - Create forms-based workflows using drag-and-drop functionality
   - Develop and manage decision logic in tabular, spreadsheet-like decision tables
   - Automate repetitive tasks within existing process flows using robotic process automation
   - Support real-time, event-driven transparency into comprehensive processes and process instances with process-visibility dashboards

## 2. Overview <a name="section2"></a>

In this section, you will do basic tasks that includes:
  - Create a Project that will contain all the artifacts
  - Create a Process that will automate the Sales Order Creation and Approvals
  - Create a Form to trigger the Process

## 3. Requirements <a name="section3"></a>

- Access to a [**SBPA Tenant**](https://github.com/evan-carr-sap/sbpa-workshop/tree/main/0%20Onboarding%20and%20Installation) and a **Windows machine** with On-premise components installed, are required to run the entire workshop.
- The Desktop Agent setup [Documentation](https://help.sap.com/docs/build-process-automation/sap-build-process-automation-dev/installing-and-updating-desktop-agent-3-to-run-automations).
- Download the [Excel File](../2%20Automation/SalesOrdersDetails.xlsx) which would be used in the Automation.

## 4. Create Business Process Project <a name="section4"></a>

1. In the **Lobby**, click on **Create**.

    ![Lobby overview](images/01_Lobby.png)

2. Click **Build an Automated Process**.

    ![Create an Automated Process](images/02_Lobby_Create.png)

3. Click **Business Process**

	![Create a Business Process](images/02_Lobby_Create_Business_Process_Project.png)

4. In the pop-up, do the following:
    - Enter **Project Name** of your choice but ensure that it is unique. 
      > - If this workshop is conducted on a shared sub-account (and not on trial or free-tier) the project name has to be unique. 
      > - Suggestion: append your User Name or User ID to the project name to make it unique. For Example: Sales Order Management XYZ.
    - Enter **Short Description** of your project, if you want.
    - Click **Create**.

    ![Fill Project information ](images/02_Lobby_Create_Business_Process_Project_filled_name.png)
    

## 5. Create Business Process <a name="section5"></a>

1. In the **Project Overview**, click on **Create**.

    ![Process Builder](images/Design_Studio/01_Design_Studio.png)


2. Click **Process**

    ![Process Builder Create Process](images/Design_Studio/02_Design_Studio_Create.png)


3. In the pop-up, do the following:
    - Enter the **Name** field.
    - Enter **Description** to your process.
    - Click **Create**.
    > The process **Identifer** field is auto-filled!

    ![Process Builder Create Process filled](images/Design_Studio/03_Design_Studio_Create_Process_filled.png)


4. Click on the **Select a Start Trigger** node.

    ![Select Starting Node](images/Design_Studio/05_Design_Studio_Process_Trigger_Settings.png)


5. Choose **New Form** in the **Forms** field.

    ![Select New form](images/Design_Studio/06_Design_Studio_Process_New_Form.png)


## 6. Create Trigger Form <a name="section6"></a>


1. In the pop-up for new form, do the following:
    - Enter the **Name** as **Order Processing Form**.
    - Enter a **Description** of your choice.
    - Click **Create**.

    > The form **Identifer** field is auto-filled!

    ![Fill Form infos](images/Design_Studio/07_Design_Studio_Create_Form.png)


2. Click **Save** and open the **Artifacts Panel**.

    ![Save and open Artifacts panel](images/Design_Studio/08_Design_Studio_Process_with_form_trigger.png)


3. Click **Order Processing Form** artifact to open the form.

    ![Click on Form artifact](images/Design_Studio/10_Design_Studio_Order_Processing_Form_Click.png)


4. Click 3 times on the **Text Input** under **INPUT FIELDS**.
    > this will add three text boxes in the form

    ![Add 3 Text Inputs](images/Design_Studio/11_Design_Studio_Order_Processing_Form_Open.png)


5. Click on the first input box, set the **Field Name** to **Order Number** and set it as **Mandatory**.

    ![Customise the first input properties](images/Design_Studio/13_Design_Studio_Order_Processing_Form_Order_Number_field.png)


6. Click on the second input box, set the **Field Name** to **Customer Name** and set it as **Mandatory**.

    ![Customise the second input properties](images/Design_Studio/14_Design_Studio_Order_Processing_Form_Customer_Name_field.png)


7. Click on the third input box, set the **Field Name** to **Order Status**.

    ![Customise the 2nd component properties](images/Design_Studio/15_Design_Studio_Order_Processing_Form_Order_Status_field.png)


#### Your Process and Trigger form is ready!
![Basics done](images/Design_Studio/16_Design_Studio_Order_Processing_Form_Designed_saved.png)


## License <a name="license"></a>

Copyright (c) 2022 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](../LICENSES/Apache-2.0.txt) file.
