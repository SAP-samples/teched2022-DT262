## Getting Started - Pre-requisite and Access to SAP Build Process Automation

In this exercise, you will access the SAP Build Process Automation Cloud Factory tenant and Register Desktop Agent to the Cloud Factory tenant.

1. The SAP Build Process Automation Desktop Agent should have now been installed onto your system. You can view it on your system tray here with the icon.

 <br>![](/exercises/ex0/images/0_1.png)

2. Go to the SAP Build Process Automation Cloud Factory tenant via the url and with the login and password provided to you by the speaker:

 - https://dt262-9vbrkgdy-applicationdevelopment.lcnc.cfapps.us10.hana.ondemand.com/lobby
 
<br>![](/exercises/ex0/images/0_2.png)
<br>![](/exercises/ex0/images/0_2_1.png)

3. You should see the following start page at “Lobby”.

<br>![](/exercises/ex0/images/0_3.png)

4. Click “Settings” at the top

<br>![](/exercises/ex0/images/0_4.png)

5. Select “Agents > Agents”

<br>![](/exercises/ex0/images/0_5.png)

6. Select “Register new agent”

<br>![](/exercises/ex0/images/0_6.png)

7. A url will be seen in the field and choose <b>Copy and Close</b> button to register this tenant to Desktop Agent.

<br>![](/exercises/ex0/images/0_7.png)

8. Now access the Desktop Agent on the taskbar and Click <b>More Actions</b>

<br>![](/exercises/ex0/images/0_8.png)

9. Click Tenants

<br>![](/exercises/ex0/images/0_9.png)

10. On Next Screen, click "Add"

<br>![](/exercises/ex0/images/0_10.png)

11. You will be prompted to add a name and domain.
- Input the following as Name - <b>DT262</b>
- For Domain, <b>input the tenant URL that you copied previously from the SAP Build Process Automation tenant</b>
- Click <b>Save</b>.

<br>![](/exercises/ex0/images/0_11.png)

12. Select your newly created tenant, per above. E.g. ‘DT262’. Click <B>Activate</b>. You might get a message <b> Are you sure you want to switch to tenant DT262</b>.

 Note: The message <b>Are you sure you want to switch to tenant DT262</b> is only when there is an alternate system already configured. In case your Desktop Agent is  fresh and empty you will not recieve this message. 

<br>![](/exercises/ex0/images/0_12.png)

<br>![](/exercises/ex0/images/0_12_1.png)


Note: Your Desktop Agent on the system tray may restart a couple of times. Once completed, the Desktop Agent will then be connected
to the SAP Build Process Automation tenant that you have access to.
<br>

13. On the next screen, insert when prompted the credentials provided to you in the email. (Example only) user: DT262_0XX( example for group 11, DT262_011) Password: <B>As provided by the speaker</b>, Next, Click <b>Okay</b> when prompted

<br>![](/exercises/ex0/images/0_13.png)
<br>![](/exercises/ex0/images/0_13_1.png)

14. Click on <b>Desktop Agent</b> again, after restart is complete.

<br>![](/exercises/ex0/images/0_14.png)

15. Click the center icon, <b>Projects</b>.

<br>![](/exercises/ex0/images/0_15.png)

16. You should see the following screen, with two modes: <B>“Interactive (attended)” or “Background (unattended)”</b>. Select <B>“Background (unattended)</b>”. Your Desktop Agent will restart a couple of times. Next click <b> OK</b> 

<br>![](/exercises/ex0/images/0_16.png)

17. Click and check that your Desktop Agent is now in “Background (unattended)” mode. You should see the following.

<br>![](/exercises/ex0/images/0_17.png)
  
18. As this SAP Build Process Automation exercise will use other elements (such as forms to trigger a process instead of a user manually starting a RPA bot from the system tray in unattended mode), we will leave this agent as unattended mode. Go back to the SAP Build Process Automation tenant via the url provided to you. From “Lobby”, navigate back to “Settings” then to “Agents > Agents”.

<br>![](/exercises/ex0/images/0_18.png)

19. You should view the following “Agents” page, with a list of “items”. Your newly registered agent should be reflected there.

<br>![](/exercises/ex0/images/0_19.png)

20. If not on the list of <b>Agents</b>, you can sort by descending, the right-most column <b>Last Updated</b>. Your agent should be the latest entry if sorted by <b>last updated</b>,
and described by: <b>your Machine name (your laptop)</b>

<br>![](/exercises/ex0/images/0_20.png)

21. Ensure that your newly created agent is in a state <b>Idle</b>, You can also further filter to your agent by using the Search field: <b>your user: E.g. DT262_0XX</b>

<br>![](/exercises/ex0/images/0_21.png)

22. Next, click on the <b> Agent Attribute</b> on the left side of the screen under <B> Agents</b>

<br>![](/exercises/ex0/images/0_22.png)

23. Next click on <b> Create Attribute</b> option and create a new <b>Predefined Attribute</b> with <B> Name</b> and <b>Value</b> as
<b>DT262_0XX </b> ( example- for group 11 it will be DT262_011)

<br>![](/exercises/ex0/images/0_23.png)

24. Now in the <b> Agent</b> list section, choose your agent and select the <B>three dots</b> and then the <b>Manage Attributes</b> under the <b>Actions</b> column. 
  
<br>![](/exercises/ex0/images/0_24.png)

25. Select the <B> Attributes</b> and <b>Value</b> based on the <b> Attribute</b> you created in the previous step i.e <b>DT262_0XX </b>

<br>![](/exercises/ex0/images/0_30.png)

<i>Note: This step helps ensures that the project will deploy and run on the bot agent specified to you. This may need to be repeated during the next project phase, where the same values above will need to be entered under Project Properties > Attributes.</i>

26. Next, click on <b>Agent Management</b> Tab and choose the <b>Add Agent</b> option.

<br>![](/exercises/ex0/images/0_27.png)

27. Select the <b> Machine Name</b> from the list and click <b> Add Agent</b>. You can get the Machine detials from agent <b> About </b> section( see second screenshot below).

<br>![](/exercises/ex0/images/0_28.png)

<br>![](/exercises/ex0/images/0_29.png)

Note: Your agent is now registered and ready to receive the workloads which we will now build using SAP Build Process Automation in the next phase.

## Summary

Now that you have completed the initial setting for the SAP Build Process Automation system and agent set up. Next step will be to extract the pre-built templates and create workflow.
Continue to - [Extend SAP S/4HANA Cloud Pre-Delivered Bot uisng SAP Build Process Automation](../ex1/README.md)
