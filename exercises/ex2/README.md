# Exercise 2 - Release, Deploy and Execute the Scenario

In this exercise, we will release and deploy the automation package to execute the scenario in SAP Build Process Automation Solution.

## Exercise 2.1 Release and Deploy Process

After completing these steps you will have created...

1. In the Process Builder, click on <b>Release</b>

<br>![](/exercises/ex2/images/21_1.png)

2.	For the first version, add a <b>Version</b> Comment and click on <b>Release</b>

<br>![](/exercises/ex2/images/21_2.png)

3. The project that was released successfully is now ready to be deployed.Click on <B> Deploy</b>

<br>![](/exercises/ex2/images/21_4.png)

4. Fill the Variables and click on <b>Confirm</b> and then <b>Deploy</b> button
- <b>SYSTEMURL_ODATA</b>: The SAP S/4HANA Cloud system Odata url. <br>The value - <b>https://my401669-api.s4hana.cloud.sap/sap/opu/odata/sap</B></br>
- <b>S4H_USER_AUTH_48M</b>: 
   - <b>login</b> - DT262_USER  
   - <b>password</b> - As provided by the speaker
- <b>BASE_FOLDER_PATH_48M</b>: Local folder path where the input file containing the data is stored as well as the output logs are generated. 
<br><i>The sample input file <b>DT262 - Create Purchase Requisitions from Excel(48M).xlsx</b> for this workshop can be downloaded from the <b>DT262</b> material folder and placed in the local folder on windows Desktop</i></br>
- <b>EMAIL_RECIPIENTS_48M</b>: Email recipient. Use your personal e-mail address to receive bot execution notifications
- <b>SAP_CLIENT</b>: leave blank

<br>![](/exercises/ex2/images/21_5.png)

<i>Note: Once you completed the variables and deployed the bot, you may need to repeat this step and re-enter all variables again, if you want to change your input. At this moment also, SAP Build Process Automation does not allow the deleting of a deployed automation.</i>

## Exercise 2.2 Run the Business Process

After completing these steps you will have...

1.	From the deployed version of the Project in the Process Builder, open the process <b>MyWorkflow_0XX</b>

<br>![](/exercises/ex2/images/22_1.png)

2.	Click on the <b>Copy</B> icon in the <b> Form Link</b> field on the right side of the screen.

<br>![](/exercises/ex2/images/22_2.png)

3. Open the form link in the new browser and fill in the following information with requester with Amount higher than 100. To see the next Manager’s Approval form on the next step, click <b>Submit</b>.

<br>![](/exercises/ex2/images/22_3.png)

4. In the <b>Lobby </b>section, Navigate to <b>Inbox</b>

<br>![](/exercises/ex2/images/22_4.png)

5. In your <B>Inbox</b> a <B>new Task</b>has arrived. Since you are acting as a manager, click on the<B> Approve</b> bbtton located at the bottom of the form.

<br>![](/exercises/ex2/images/22_5.png)

6. After the approval the <B>Create Purchase Requisitions from Excel(48M)</b> Automation will be triggered. The automation will read the inputs from the Excel File and use the system information and credentials to create a purchase requisition in the SAP S/4HANA Cloud.

7. The bot will run automatically, and an output report will be sent to the email specified per the variable <b>EMAIL_RECIPIENTS_48</b> with a copy of the same stored on the error or the success folder located in your base folder (variable - <b>BASE_FOLDER_PATH_48M</b>).

<br>![](/exercises/ex2/images/22_7.png)

8. You can also cross-check the posted data in the SAP S/4HANA Cloud system, against the data in the post-run excel that was sent to the specified recipient email.Please use the below url and login detials.

 - SAP S/4HANA System:<b>https://my401669.s4hana.cloud.sap/ui#</b>
 - Login: <b>DT262_0XX</b>
 - Password: <b> As provided by the Speaker</b>
 - Search for the app: <B> Manage Purchase Requisition</b>

<br>![](/exercises/ex2/images/22_8.png)


## Summary

Congratulations! You have now successfully modified a Pre-built Bot using the SAP Build Process Automation. We have looked at a basic scenario that leverages the Workflow Management, Decision Logic and Approval Forms to create a Business Process.


