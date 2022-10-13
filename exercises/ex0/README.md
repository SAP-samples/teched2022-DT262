<b>Access to SAP Process Automation</b>

In this exercise, you will access the SAP Process Automation Cloud Tenant and Register Desktop Agent to the Cloud Tenant.

## Level 2 Heading

After completing these steps you will have....

1.The SAP Build Process Automation Agent should have now been installed onto your system. You can view it on your system tray here with the icon.

<br>![](/exercises/ex0/images/0_1.png)

2.	Insert this code.

<br>![](/exercises/ex0/images/0_2.png)
3. Go to the SAP Process Automation tenant via the url and with the login and password provided to you by the speaker:

https://dt262-9vbrkgdy-applicationdevelopment.lcnc.cfapps.us10.hana.ondemand.com/lobby
<br>![](/exercises/ex0/images/0_3.png)

4. You should see the following start page at “Lobby”.

5. Click “Settings” at the top

6.Select “Agents > Agents List”

7. Select “Register new agent”

9. A URL will be seen in the field.Copy the link.

<B>SAP RPA Agent: Registering your tenant on the agent</b>

1. Click “More Actions”
2. Click Tenants
3. On Next Screen, click "Add"
4. You will be prompted to add a name and domain.
- Input the following as Name.
- For Domain, input the tenant URL that you copied previously from the SAP Process Automation tenant.
- Click “Save”.
5. (1) Select your newly created Tenant, per above. E.g. ‘SAP Process Automation – Your initials’.

(2) Click “Activate”.

Note: Your Desktop Agent on the system tray may restart a couple of times. Once completed, the RPA Desktop Agent will then be connected
to the SAP Process Automation tenant that you have access to

On the next screen, insert when prompted the credentials provided to you in the email. (Example only) user: P12345… per email Password: per email (2) Click “Okay” when prompted

Click on Desktop Agent again, after

restart is complete.

(2) Click the center icon, “Projects”.

(1) You should see the following screen, with two modes: “Interactive (attended)” or “Background (unattended)”. (2) Select “Background (unattended)”. (3) Your Desktop Agent will restart a couple of times.

Click and check that your Desktop Agent is now in “Background (unattended)” mode. You should see the following.

As this SAP Process Automation exercise will use other elements (such as forms to trigger a process instead of a user manually starting an RPA bot from the system tray in attended mode), we will leave this agent as unattended.

<b>Exercise 3</b>

Go back to the SAP Process Automation tenant via the url provided to you:


(2) From “Lobby”, navigate back to “Settings” then to “Agents > agent list”.

(1) You should view the following “Agents” page, with a list of “items”. Your newly registered agent should be reflected there.

(2) If not on the Agents List, you can sort by descending, the right-most column Last Updated. Your agent should be the latest entry if sorted by last updated,

and described either by:

a. your user (as sent in the email)

e.g. ‘P12345…’, or

b. your Machine name (your

laptop)

(3) Ensure that your newly created agent is in a state “Idle”

You can also further filter to your agent by using the Search field:your user: E.g. ‘P12345…’

(1) On the right, head to the column “Actions”, and select the three dots.

(1) Select Manage Attributes

(1) Select Attributes “User” Enter under “Values”, your user ID provided as per the email:E.g. ‘spaworkshop_(your participant ID)’

(2) Click Confirm.

Note: This step helps ensures that the project will deploy and run on the bot agent specified to you. This may need to be repeated during the next project phase, where the same values above will need to be entered under Project Properties > Attributes.

(1) You can also click through to view more details, such as the latest version and mode of the agent.

(2) Make sure the mode is as “unattended”. From here, your agent is now registered and ready to receive the workloads which we will now build using SAP Process Automation in the next phase.










## Summary

Now that you have ... 
Continue to - [Exercise 1 - Exercise 1 Description](../ex1/README.md)
