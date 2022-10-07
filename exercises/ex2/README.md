# Exercise 2 - Release and Deploy

In this exercise, we will release the and deploy the automation package to execute the scenario in SAP Process Automation Solution.

## Exercise 2.1 Sub Exercise 1 Description

After completing these steps you will have created...

1. In the Process Builder, click on <b>Release</b>
<br>![](/exercises/ex2/images/02_01_0010.png)

2.	For the first version, add a <b>Version</b> Comment if needed and click on <b>Release</b>

3. For the additional version, choose the type of <B>version</b>, add a Version Annotation if needed and click on <b>Release</b>.

4. The project Released successfully is ready to be deployed.

5. Click on the <b>Save</b> Button to Save the Workflow From the released version of the business process project in the Process Builder, click on <b>Deploy</b>

6. Fill the Variables and click on Confirm
- SYSTEMURL_ODATA: ODATA URL of S4 system. For this workshop use value „https://my300183-api.s4hana.ondemand.com/sap/opu/odata/sap”
- BASE_FOLDER_PATH_48M:local folder path, where the file containing Purchase Requisitionsis stored. The sample input file for this workshop can be downloaded from here 
- EMAIL_RECIPIENTS_48M:Email recipient. 
Use your own e-mail address to receive bot execution notifications
- S4H_USER_AUTH_48M: Ask this to your instructor.
- SAP_CLIENT: leave blank

<i>Note: Once you completed the variables and deployed the bot, you may need to repeat this step and re-enter all variables again, if you want to change your input. At this moment also, SAP Process Automation does not allow the deleting of a deployed automation.</i>

## Exercise 2.2 Run the Business Process

After completing these steps you will have...

1.	From the deployed version of the Business Process Project in the Process Builder, open the process <b>MyWorkflow</b>
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc = 0.
    response->set_status( i_code = 200
                     i_reason = 'Everything is fine').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex2/images/02_02_0010.png)

## Summary

You've now ...

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
