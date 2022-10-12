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

<br>![](/exercises/ex1/images/ex1_1.png)

2. Filter by Project Type <b>Business Process</b> in the checkbox on left menu and search for keyword <b>Purchase Requisition</b>
```abap
response->set_text( |Hello World! | ). 
```
3. Once the Project Name <b>Create Purchase Requisitions from Excel (48M)</b>is found, click on the <b>Add</b> button and select <b>Create from Template</b>.

4. Give the Name of the Project.E.g.,“Create Purchase Requisitions”+ "+" + your group number (sample- Create Purchase Requisitions_001 for group 1)

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
  
7. In the pop-up for new form, do the following
  - Enter the Name as <b>InputForm:PR_Details</b>
  - Enter a Description(optional)
  - Click <b>Create</b>
  
 8. Double Click on the <b>InputForm:PR_Details</b> is submitted tab
  
 9. The newly created form design console will be opened.
  
 10. Drag and drop the Paragraph into the canvas and provide the following text:
  <b>Dear requester, please enter the following details of your purchase requisition below.</b>
  
 11. Drag and Drop the Text Input from the left to the canvas. Rename it to <b>PR Numberand</b> check the required check box from right menu.
  
 12. Similarly create the input fields <b>PRAmount (Number)</b>, <b>Requester Name(Text)</b> and <b>Requisition date (Date)</b>. Mark all the fields as <b>Required</b>.
  
 13. Click on <b>Save</b>. <b>The Process Trigger form is ready !!</b>
  
 14. Return to the Automation tab.
  
 15. Click <b>+</b>icon next to Input Form and select <b>Controls -> Condition</b>
  
 16. On the details panel for Condition, click on <b>Open Condition Editor</b>
  
 17. In the Branch condition you will need to Provide the Item to be compared, the operator and value to be compared.Click on Each text box to select the following value:
  - Select Item:PR Amount
  - Operator:is less than or equal
  - Value:100
  
 18. The branch condition should look like this.
  
 19. Click <B>Save</b>
  
 20. The Condition has two branches <b>If</b> (when condition is true) and <b>Default</b>(when condition is false). 
  
 21. Click the <B>+</b> icon on the If branch to insert an Automation <B>Automations-> Create Purchase Requisitions From Excel</b> 
  <i>This will insert the Automation that will be executed when the value of PR Amount is less than 100</i>
  
 22. The Create Purchase Requisitions From Excel Automation will be inserted into the Process flow.
 
 23. To handle PR with amount Greater than 100, an approval from Manager is required, hence an approval form needs to be created.
 To Create a Manager’s Approvalform,click on the <B>+</b>icon next to the Default Branch and select <b>+ New Approval Form</b>
 
 24. Give the Name of the Form :<B>Approval: Manager Approval</b>, finally click on <b>Create</b>
 
 25. Manager’s Approval form will be inserted
 
 26. Double-click on the Manager’s Approval Form inserted form to open the form editor.
 Insert Paragraph for Welcome Message:
 - Drag and Drop the <b>Paragraph </b>from the left Menu and Insert the following Text <i>“Dear Manager, please find details of a new purchase requisition for your review”</i>
  
 27. Drag and Drop the Text Inputs from left menu and name it <B>PR Number</b> and set it <b>Read Only</b> from rightMenu
  
 28.Similarly create <b>PR Amount(Number)</b> and <b>Requester Name(Text)</b> in the formand set them read only as well
  
 29. Click on the <b>Save</b> Button
  
 30. Navigate Back to the Process and Click on <b>Approval:Manager Approval</b> Form. From the Right Menu select<b> General</b> Tab
  
 31. In the Subject field provide <b>PR_Number </b>value as given in the Snapshot.  
  
 32. Similarly for User field  select <b>Process Started By</b>
  
 33. Click on the Inputs tab from the Inputs. Select <b>PR Amount, PR Number </b>and <b>Requestor Name</b> as input from the form.
  
 34. To generate an approval notification,click on the <b>+</b>icon on the Approve branch. From the menu choose Forms -><b>+New Form </b> to create a new form. 
  
 35. Name the form as <b>Notification: PR Accepted</b>
  
 36. <b>Notification: PR Accepted</b> form is inserted into the canvas. <b>Double click</b> on the to see the design console.
  
 37. Design the form with the following fields:
  - Paragraph with Value <b>Dear requestor, your PR was accepted.</b>
  - <b>PR Number</b>: Read only Text field
  - <b>PR Amount</b>: Read only Number field
  - <b>Requestor Name</b>: Read Only Text Field
  Save the form and Navigate back to the Process flow.
  
  38. Click on the <b>Notification: PR Accepted</b> form.
  
  39. Go to General tab from the left menu and provide the following inputs:
  - Subject: <b>PR Number followed by approved</b>
  - Users: <b>Process Started By</b>
  
  40. Select Inputs tab from the right menu and select the Inputs as given in snapshot.
  
  41. Click on the <b>Reject</b> branch of the <b>Approval: Manager</b> Approval Form. Click on the <b>+</b>icon on the Reject branch. From the menu choose <b>Forms -> +New Form</b> to create a new form.
  
  42. Give the name as <b>Notification: PR Rejected</b>.
  
  43. Double click on the newly created form and provide the following fields:
  - Paragraphwith the following text : <i>Dear Requestor, your PR request was rejected. Please contact purchasing for more details</i>. Click submit to end the workflow
  - <b>PR Number</b> of type Text and Read Only
  - <b>PR Amount</b> of type Number and Read Only
  
  44. Select the General tab from the right menu and set the subject as <b>PR Number(form input)</b> followed by<b> rejected</b>.
  
  45. Click on the <b>+</b>icon on the Submit branch of the <b>Notification: PR_AcceptedForm </b>and from the menu choose <b>Automation->Create Purchase Requisition From Excel</b>
  
  46.The Automation is added to the Process.
  
  47. Click on the <b>+</b>icon on the Success branch and from the menu select <b.Controls-> End</b>
  
  48. Similarly click the <b>+</b> icon on the Submit branch ofthe <b>Notification:PR Rejected </b>Form and select <b>Controls->End</b>
  
  49.When complete,the Process should be looking similar to the snapshot with no errors. Click on <b>Save</b>.


## Summary

You have now acquired the SAP S/4HANA Cloud Pre-built content from the bot store and extended the Pre-Delivered Bot uisng SAP Process Automation to include workflow feature.

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

