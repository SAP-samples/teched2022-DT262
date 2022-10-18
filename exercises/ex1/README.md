# Exercise 1 - Extend SAP S/4HANA Cloud Pre-Delivered Bot uisng SAP Build Process Automation

Creating purchase requisitions(PR) manually is not just time taking, but also a tedious and monotonous task. The Create Purchase Requisitions from Excel (48M) simplifies the creation of purchase requisitions. Customers can give the purchase requisition details as an input to the bot by compiling them into one template excel file. The automation reads those details and creates purchase requisitions and sends the report email to the recipients.

During this exercise, the following extensions will be made to the  pre-delivered content:
- An input form for the User to enter PR Number, PR Amount, Requester Number and Requisition Date.
- An Approval form for the Manager to see the PR information to Accept or Reject.
- Notification Form for the User to show if the PR is accepted or rejected.
- Workflow to Bootstrap the process, where user first submits the form and based on PR Amount the PR is sent forApproval to Manager. Only after Manager’s approval or PR with Low amount the Purchase Requisition is created using the pre-built bot.

## Exercise 1.1 Acquire the Pre-built Bot Template Project From the Store

After completing these steps you will have aquire the SAP S/4HANA Cloud Out-of-box prebuilt template for Purchase Requisition(PR) creation from SAP Bot Store and extend the scenario to include the approval process via the Workflow.

1. Login to the SAP Build Process Automation Tenant using below url and Navigate to <b>Store</b>

https://dt262-9vbrkgdy-applicationdevelopment.lcnc.cfapps.us10.hana.ondemand.com/lobby

<br>![](/exercises/ex1/images/ex1_1.png)

2. Choose Filter by Project Type <b>Business Process</b> in the checkbox on left menu and search for keyword <b>Purchase Requisition</b>

<br>![](/exercises/ex1/images/ex1_2.png)

3. Once the Project Name <b>Create Purchase Requisitions from Excel (48M)</b>is found, click on the <b>Add</b> button and select <b>Create from Template</b>.

<br>![](/exercises/ex1/images/ex1_3.png)

4. Give the Name of the Project. E.g.,<b>“Create Purchase Requisitions”+ "_" + your group number</b> (sample- Create Purchase Requisitions_011 for group 11)

<br>![](/exercises/ex1/images/ex1_4.png)

5. Next, choose <b>Create </b>

<br>![](/exercises/ex1/images/ex1_5.png)

6. A new window opens where you can see the bot artifacts.

<br>![](/exercises/ex1/images/ex1_6.png)
  
7. Click <B>Settings </b> as indicated by the gear icon.

<br>![](/exercises/ex1/images/ex1_7.png)
  
8. You will need to set the <b>Project Attributes</b>, for your project, to ensure that the deployed project will run against the right agent with the right specified attributes.

<br>![](/exercises/ex1/images/ex1_8.png)
  
9. On the next screen, click on <B>Attributes</b> and Select Attributes: <b>User</b>

<br>![](/exercises/ex1/images/ex1_10.png)
  
10. Enter values unique to your project ID, as defined in the second last step of the previous Registration document:E.g. DT262_"Group Number" (Sample DT262_011 for group 11)

<br>![](/exercises/ex1/images/ex1_9.png)

## Exercise 1.2 Create Business Process

After the <b>Create Purchase Requisitions from Excel (48M)</b> bot extraction from the SAP Bot Store, we will now define the approval process for this bot by including the workflow technology.

1.	When you open a project, you are taken to the project <b>Overview</b> tab.The list of all artifacts is displayed.

<br>![](/exercises/ex1/images/ex1_6.png)

2.	In the Overview tab, click on <B>+</b> icon -> <b>Create</b> 

<br>![](/exercises/ex1/images/ex12_2.png)
  
3. To create a new business process,click <b>Process</b> button.

<br>![](/exercises/ex1/images/ex12_3.png)
  
4. In the pop-up, do the following:
  - Enter the Name field. E.g. <b> MyWorkflow_XXX </b>(Sample MyWorkflow_011 for group 11)
  - Enter a description(optional) - <b>Myworkflow_0XX</b>
  - Choose <b>Create </b>
  
<br>![](/exercises/ex1/images/ex12_4.png)
  
5. Click <b>+</b> button to start a Trigger

<br>![](/exercises/ex1/images/ex12_5.png)
  
6. On the available Forms dropdown, choose <b>New Form</b> in the Forms field

<br>![](/exercises/ex1/images/ex12_6.png)
  
7. In the Create Form pop-up window, do the following:
  - Enter the Name as <b>InputForm: PR_Details</b>
  - Enter a Description(optional)
  - Click <b>Create</b>
  
 <br>![](/exercises/ex1/images/ex12_7.png)
  
 8. Click on the <b>InputForm: PR_Details</b> and next select <b> Open Editor</b> option.
 
 <br>![](/exercises/ex1/images/ex12_8.png)
  
 9. The newly created form design console will be opened.
 
 <br>![](/exercises/ex1/images/ex12_9.png)
  
 10. Drag and drop the Paragraph into the canvas and provide the following text:
  <b>Dear requester, please enter the following details of your purchase requisition below.</b>
  
  <br>![](/exercises/ex1/images/ex12_10.png)
  
 11. Drag and Drop the Text Input from the left to the canvas. Rename it to <b>PR Number</b> and check the <b>Required</b> check box from right menu.
 
 <br>![](/exercises/ex1/images/ex12_11.png)
  
 12. Similarly create the input fields <b>PR Amount (Number)</b>, <b>Requester Name(Text)</b> and <b>Requisition Date (Date)</b>. Mark all the fields as <b>Required</b>.
 
 <br>![](/exercises/ex1/images/ex12_12.png)
  
 13. Click on <b>Save</b>. <b>The Process Trigger form is ready !!</b>
 
 <br>![](/exercises/ex1/images/ex12_13.png)
  
 14. Return to the <b>MyWorkflow_0XX</b> tab.
 
 <br>![](/exercises/ex1/images/ex12_14.png)
  
 15. Click <b>+</b> icon next to Input Form and select <b>Controls -> Condition</b>
 
 <br>![](/exercises/ex1/images/ex12_15.png)
  
 16.On details panel for Condition, click on <b>Open Condition Editor</b>
 
 <br>![](/exercises/ex1/images/ex12_16.png)
  
 17. In the Branch condition you will need to provide the item, the operator and value to be compared. Click on each text box to select the following value:
  - Select Item: <b>PR Amount</b>
  - Operator:<b>is less than or equal</b>
  - Value:<b>100</b>
  
 <br>![](/exercises/ex1/images/ex12_17.png)
  
 18. The branch condition should look like this.
 
 <br>![](/exercises/ex1/images/ex12_18.png)
  
 19. Click <B>Save</b>
 
 <br>![](/exercises/ex1/images/ex12_19.png)
  
 20. The Condition has two branches <b>If</b> (when condition is true) and <b>Default</b> (when condition is false). 
  
 <br>![](/exercises/ex1/images/ex12_20.png)
  
 21. Click the <B>+</b> icon on the If branch to insert an Automation <B>Automations-> Create Purchase Requisitions From Excel</b> 
  <i>This will insert the Automation that will be executed when the value of PR Amount is less than 100</i>
  
 <br>![](/exercises/ex1/images/ex12_21.png)
  
 22. The <B>Create Purchase Requisitions From Excel(48M)</b> Automation prebuilt bot will be inserted into the Process flow.
 
 <br>![](/exercises/ex1/images/ex12_22.png)
 
 23. To handle PR with amount Greater than 100, an approval from Manager is required, hence an approval form needs to be created.
  To Create a Manager’s Approval form,click on the <B>+</b>icon next to the <B>Default</b> Branch and select <b>+ New Approval Form</b>
 
 <br>![](/exercises/ex1/images/ex12_23.png)
 
 24. Give the Name of the Form :<B>Approval: Manager Approval</b>, finally click on <b>Create</b>
 
 <br>![](/exercises/ex1/images/ex12_24.png)
 
 25. Manager’s Approval form will be inserted
 
 <br>![](/exercises/ex1/images/ex12_25.png)
 
 26. Double-click on the Manager’s Approval Form inserted form to open the form editor.
 Insert Paragraph for Welcome Message:
 - Drag and Drop the <b>Paragraph </b>from the left Menu and Insert the following Text <i>“Dear Manager, please find details of a new purchase requisition for your review”</i>
 
 <br>![](/exercises/ex1/images/ex12_26.png)
  
 27. Drag and Drop the Text Inputs from left menu and name it <B>PR Number</b> and set it <b>Read Only</b> from right menu
 
 <br>![](/exercises/ex1/images/ex12_27.png)
  
 28.Similarly create <b>PR Amount(Number)</b> and <b>Requester Name(Text)</b> in the form and set them read only as well
 
 <br>![](/exercises/ex1/images/ex12_28.png)
  
 29. Click on the <b>Save</b> Button
 
 <br>![](/exercises/ex1/images/ex12_29.png)
  
 30. Navigate Back to MyWorkflow_0XX and Click on <b>Approval:Manager Approval</b> Form. From the Right Menu select<b> General</b> Tab
 
  <br>![](/exercises/ex1/images/ex12_30.png)
  
 31. In the Subject field provide <b>PR_Number </b>value as given in the Snapshot.  
 
 <br>![](/exercises/ex1/images/ex12_31.png)
  
 32. Similarly for User field  select <b>Process Started By</b>
 
<br>![](/exercises/ex1/images/ex12_32.png)
  
 33. Click on the Inputs tab from the Inputs. Select <b>PR Amount, PR Number </b>and <b>Requestor Name</b> as input from the form. Click <b> Save</b>
 
  <br>![](/exercises/ex1/images/ex12_33.png)
  
 34. To generate an approval notification,click on the <b>+</b>icon on the Approve branch. From the menu choose Forms -><b>+New Form </b> to create a new form. 
  
 <br>![](/exercises/ex1/images/ex12_34.png)
 
 35. Name the form as <b>Notification: PR Accepted</b> and choose <b>Create</b>
 
 <br>![](/exercises/ex1/images/ex12_35.png)
  
 36. <b>Notification: PR Accepted</b> form is inserted into the canvas. <b>Double click</b> on the to see the design console.
  
  <br>![](/exercises/ex1/images/ex12_36.png)
  
 37. Design the form with the following fields:
  - Paragraph with Value <b>Dear requestor, your PR was accepted.</b>
  - <b>PR Number</b>: Read only Text field
  - <b>PR Amount</b>: Read only Number field
  - <b>Requestor Name</b>: Read Only Text Field
  <b>Save</b> the form and Navigate back to the MyWorkflow_0XX.
  
  <br>![](/exercises/ex1/images/ex12_37.png)
  
  38. Click on the <b>Notification: PR Accepted</b> form and click on the <b> General</b> tab.
  
  <br>![](/exercises/ex1/images/ex12_38.png)
  
  39. In the General tab from the left menu and provide the following inputs:
  - Subject: <b>PR Number</b> followed by <bApproved</b>
  - Users: <b>Process Started By</b>
  
  <br>![](/exercises/ex1/images/ex12_39.png)
  
  40. Select Inputs tab from the right menu and select the Inputs as given in snapshot.
  
  <br>![](/exercises/ex1/images/ex12_40.png)
  
  41. Click on the <b>Reject</b> branch of the <b>Approval: Manager</b> Approval Form. Click on the <b>+</b>icon on the Reject branch. From the menu choose <b>Forms -> +New Form</b> to create a new form.
  
  <br>![](/exercises/ex1/images/ex12_41.png)
  
  42. Give the name as <b>Notification: PR Rejected</b> and choose <b>Create</b>.
  
  <br>![](/exercises/ex1/images/ex12_42.png)
  
  43. Double click on the newly created form and provide the following fields:
  - Paragraph with the following text : <i>Dear Requestor, your PR request was rejected. Please contact purchasing for more details</i>. 
  - <b>PR Number</b> of type Text and Read Only
  - <b>PR Amount</b> of type Number and Read Only Save the form and Navigate back to the MyWorkflow_0XX.
  
  <br>![](/exercises/ex1/images/ex12_43.png)
  
  44. Click on the Notification: PR Rejected form and select the General tab from the right menu and set the subject as <b>PR Number(form input)</b> followed by<b> Rejected</b>. In <b>User</b> field  select <b>Process Started By</b>
  
  <br>![](/exercises/ex1/images/ex12_44.png)
  
  45. Click on the <b>+</b>icon on the Submit branch of the <b>Notification: PR_AcceptedForm </b>and from the menu choose <b>Automation->Create Purchase Requisition From Excel</b>
  
  <br>![](/exercises/ex1/images/ex12_45.png)
  
  46.The Automation is added to the Process.
  
  <br>![](/exercises/ex1/images/ex12_46.png)
  
  47. Click on the <b>+</b>icon on the Success branch and from the menu select <b>Controls-> End</b>
  
  <br>![](/exercises/ex1/images/ex12_47.png)
  
  48. Similarly click the <b>+</b> icon on the Submit branch ofthe <b>Notification:PR Rejected </b>Form and select <b>Controls->End</b>
  
  <br>![](/exercises/ex1/images/ex12_48.png)
  
  49.When complete,the Process should be looking similar to the snapshot with no errors. Click on <b>Save</b>.

 <br>![](/exercises/ex1/images/ex12_49.png)

## Summary

You have now acquired the SAP S/4HANA Cloud Pre-built content from the bot store and extended the Pre-Delivered Bot uisng SAP Build Process Automation to include workflow feature.

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

