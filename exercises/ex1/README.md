# Exercise 1 - Extend SAP S/4HANA Cloud Pre-Delivered Bot uisng SAP Process Automation

Creating purchase requisitions manually is not just time taking, but also a tedious and monotonous task. The Create Purchase Requisitions from Excel (48M) simplifies the creation of purchase requisitions. Customers can give the purchase requisition details as an input to the bot by compiling them into one template excel file. The automation reads those details and creates purchase requisitions and sends the report email to the recipients.

During this exercise, the following extensions will be made to the  pre-delivered content:
- An input form for the User to enter PR Number, PR Amount, Requester Number and Requisition Date.
- An Approval form for the Manager to see the PR information to Accept or Reject.
- Notification Form for the Userto show if the PR is accepted or rejected.
- Workflow to Bootstrap the process, where user first submits the form and based on PR Amount the PR is sent forApproval to Manager. Only after Manager’s approval or PR with Low amount the Purchase Requisition is created using the pre-built bot.

## Exercise 1.1 Acquire the Pre-built Bot Template Project From the Store

After completing these steps you will have created...

1. Login to the SAP Build Process Automation Tenant using below url and Navigate to <b>Store</b>
<br>![](/exercises/ex1/images/01_01_0010.png)

2. Filter by Project Type <b>Process Automation</b> in the checkbox on left menu and search for keyword <b>Purchase Requisition</b>
```abap
response->set_text( |Hello World! | ). 
```
3. Once the Project Name <b>Create Purchase Requisitions from Excel (48M)</b>is found, click on the arrow next to Open Button and select <b>Create from Template</b>.

4. Give the Name of the Project.E.g.,“Create Purchase Requisitions”+ <your participant number>

5. Next, choose <b>Create </b>

6. To see the newly created project,navigate back to <b>Lobby</b> from top menu. You should find the newly created project here.
  
7. Click on the project name to open it.
  
8. Click <B>Settings </b> as indicated by the gear icon.
  
9. You will need to set the <b>Project Attributes</b>, for your project, to ensure that the deployed project will run against the right agent with the right specified attributes.
  
10. On the next screen, click on <B>Attributes</b>.
  
11. Select Attributes: <b>User</b>
  
12. Enter values unique to your project ID, as defined in the second last step of the previous Registration document:E.g. spaworkshop_"your participant ID"


## Exercise 1.2 Create Business Process

After completing these steps you will have...

1.	When you open a project, you are taken to the project Overview tab.The list of all include artifacts is displayed.

2.	In the Overview tab, click on + icon -> <b>Create</b> 
  
3. To create a new business process,click <b>Process</b> button.
<br>![](/exercises/ex1/images/01_02_0010.png)
  
4. In the pop-up, do the following:
  - Enter theNamefield. E.g. “MyWorkflow”
  - Enter a description(optional)
  - Choose Create
  
5. Click <b>Select a Start Trigger</b>
  
6. On the available Forms dropdown, choose <b>New Form</b> in the Forms field
  


## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

