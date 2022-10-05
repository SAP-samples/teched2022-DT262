# Exercise 1 - Exercise 1 Description

Creating purchase requisitions manually is not just time taking, but also a tedious and monotonous task. The Create Purchase Requisitions from Excel (48M) simplifies the creation of purchase requisitions. Customers can give the purchase requisition details as an input to the bot by compiling them into one template excel file. The automation reads those details and creates purchase requisitions and sends the report email to the recipients.

During this exercise, the following extensions will be made to the  pre-delivered content:
- An input form for the User to enter PR Number, PR Amount, Requester Number and Requisition Date.
- An Approval form for the Manager to see the PR information to Accept or Reject.
- Notification Form for the Userto show if the PR is accepted or rejected.
- Workflow to Bootstrap the process, where user first submits the form and based on PR Amount the PR is sent forApproval to Manager. Only after Manager’s approval or PR with Low amount the Purchase Requisition is created using the pre-built bot.

## Exercise 1.1 Sub Exercise 1 Description

After completing these steps you will have created...

1. Click here.
<br>![](/exercises/ex1/images/01_01_0010.png)

2.	Insert this line of code.
```abap
response->set_text( |Hello World! | ). 
```



## Exercise 1.2 Sub Exercise 2 Description

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex1/images/01_02_0010.png)


## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

