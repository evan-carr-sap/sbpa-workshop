## Table of Contents
- [Adding an Action](#section1)
    - [Create and Configure the BTP Destination](#section1-destination)
    - [Create an Action Project](#section1-createproject)
    - [Configure Action Project](#section1-actionproject)
    - [Use Action from Process](#section1-actioncall)
- [Summary](#summary)


## Adding an Action <a name="section1"></a>
**Actions** encapsulates APIs as actions in the business process.

Actions projects can be created in 3 different ways:
- SAP Graph allows you to consume all business data in the form of a semantically connected data graph accessed via a single unified and powerful API
- Any API specification available in the Business Accelerator Hub
- Uploading a custom API specification
    > - Only EDMX, XML, and JSON files are supported and the file size is limited to 5 MB.
    > - Open API specification files with versions 2.x.x and 3.x.x of JSON type are supported.

### Create and Configure the BTP Destination<a name="section1-destination"></a>
1. An HTTP Destination was already created during the prerequisites with properties. This destination will be made available from the Build Process Automation Lobby for use in Action and Business Processes.


| Property                                    | Value  |
|:--------------------------------------------|:-------|
| sap.applicationdevelopment.actions.enabled  | true   |
| sap.processautomation.enabled               | true   |

2. Click on **Settings** in the Build Process Automation Lobby

    ![Build Process Automation Lobby Settings](images/01_Lobby.png)

3. Click on **Destinations** on the left-hand panel

    ![Settings Page](images/01_Settings.png)

4. Click on **New Destination**

    ![Destinations Page](images/01_New_Destination.png)

5. Search for the destination and select it from the list

    ![Select Destination](images/01_Select_Destination.png)

### Create an Action Project<a name="section1-createproject"></a>
1. In the **Lobby**, click on **Create**.

    ![Lobby overview](images/02_Lobby.png)

2. Click **Build an Automated Process**.

    ![Create an Automated Process](images/02_Lobby_Create.png)

3. Click **Actions**

	![Create an Action Project](images/02_Lobby_Create_Action_Project.png)

4. Click **Business Accelerator Hub**

    ![Business Accelerator Hub](images/02_Lobby_Create_Action_Project_BAH.png)

5. Search for '**Sales Order**' and select '**Sales Order (A2X)**'

    ![Sales Order API Specification](images/02_Lobby_Create_Action_Project_BAH_Sales_Order.png)

6. Click **Next**

    ![Confirm Sales Order API](images/02_Lobby_Create_Action_Project_BAH_Sales_Order_Accept.png)

7. In the pop-up, do the following:
    - Enter **Project Name** of your choice but ensure that it is unique. 
      > - If this workshop is conducted on a shared sub-account (and not on trial or free-tier) the project name has to be unique. 
      > - Suggestion: append your User Name or User ID to the project name to make it unique. For Example: Sales Order Management XYZ.
    - Edit the **Short Description** of your project, if you want.
    - Click **Create**.

    ![Fill Project information ](images/02_Lobby_Create_Action_Project_BAH_Sales_Order_Accept_filled.png)

### Configure Action Project <a name="section1-actionproject"></a>

1. When the Action project opens search for '**Create**', open the dropdown menu called **Sales Order Header**, and select the **POST** option with the label **/A_SalesOrder**. Add this action to the project.

    ![Select API Endpoint](images/03_Select_Action.png)

2. In the body of the post we only want to keep the fields with the data we will use when creating the sales order. Select all fields using the checkbox at the header level of the body table and remove all fields from the table.

    ![Remove Fields](images/03_Remove_Fields.png)

3. Add the following fields back to the Action by first clicking the plus on the body table. Then search and select the fields until all are checked. Finally, add these fields to the action.
    - OrganizationDivision
    - DistributionChannel
    - SoldToParty
    - SalesOrderType
    - PurchaseOrderByCustomer
    - SalesOrganization
    ![Add Actions](images/03_Add_Actions.png)

4. Repeat steps 2 & 3 above under the Output tab until only the required fields are returned from the action
    - SalesOrder
    ![Set Outputs](images/03_Set_Outputs.png)

5. We now want to format the full URL path to our OData service and retrieve the CSRF token required for performing a POST request. Click the settings button in the upper right hand corner

    ![Open Settings](images/03_Settings.png)

6. Click on the CSRF menu on the left-hand panel in the settings. Then toggle the switch to enable retrieval of the CSRF token and use the endpoint '**/$metadata**'.

    ![CSRF Token Settings](images/03_CSRF.png)

7. Click on the URL Prefix menu on the left-hand panel and set the Resource Path to '**/sap/opu/odata/sap/API_SALES_ORDER_SRV**' and click **Save** to confirm the changes.

    ![URL Prefix Settings](images/03_URL_Prefix.png)

    The Destination URL, URL Prefix, CSRF End Point, and Action End Point all work in conjunction to make the API call for creating the sales order. First, the Destination URL and URL Prefix are concatenated to form the Base URL used throughout the Action project.
    > Base URL = Destination URL + URL Prefix
    
    If a request is used in the Action that intends to add, delete, or modify data, a CSRF token must first be requested. The URL used for retrieving this token is the Base URL from above and the CSRF End Point defined in the settings of the Action project.
    > CSRF URL = Base URL + CSRF End Point
    
    Finally, the Action request is made using the Base URL defined above and the Entity defined in the Action.
    > Action URL = Base URL + Action Entity

8. Now test the Action by first clicking the **Test** tab, selecting the **Destination** option, and selecting the destination imported from the dropdown menu. Proper input values must be provided to all input fields available, please use values based on your system's configuration. Click **Test** to create the sales order. The Action will return a Sales Order number if it was successful.

    ![Test Action](images/03_Test.png)

9. Click the **Release** Button in the upper right-hand corner.

    ![Release Action](images/03_Release.png)

10. Note any changes made during the release for understanding updates between releases.

    ![Confirm Release](images/03_Release_Confirm.png)

11. Click the **Publish to Library** button in the upper right-hand corner.

    ![Publish to Library](images/03_Publish.png)

12. Click **Publish** to confirm to make the project available in the library.

    ![Confirm Publish](images/03_Publish_Confirm.png)

### Use Action from Process <a name="section1-actioncall"></a>


## SUMMARY <a name="summary"></a>

###### You have successfully created and configured the action. This API call will create the Sales Order in the S/4HANA system.

  You are now able to:
  - [x] Create and use a Destination with SBPA.
  - [x] Create and customize Action projects.
  - [x] Call API's from a process via Actions.
