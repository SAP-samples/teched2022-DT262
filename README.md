# Session ID - Session Title

## Description

This repository contains the material for the SAP TechEd 2022 session called DT262 - Execute Bots Rapidly in SAP S/4HANA Cloud with SAP Build Process Automation.  

## Overview

In this session,you will learn how to use the SAP Build Process Automation to modify a pre-built bot i.e.,Create Purchase Requisitions from Excel (48M). 

The pre-built bot is designed to simplify the creation of purchase requisitions. The user can give the purchase requisition details as an input to the bot by compiling them into one template excel file. The bot reads those details and creates purchase requisitions and sends the report email to the recipients. 

During this exercise, the following extensions will be made to the  pre-delivered content:
- An input form for the User to enter PR Number, PR Amount, Requester Number and Requisition Date.
- An Approval form for the Manager to see the PR information to Accept or Reject.
- Notification Form for the User to show if the PR is accepted or rejected.
- Workflow to Bootstrap the process, where user first submits the form and based on PR Amount the PR is sent forApproval to Manager. Only after Manager’s approval or PR with Low amount the Purchase Requisition is created using the pre-built bot.

## Requirements

The requirements to follow the exercises in this repository are...

## Exercises

Provide the exercise content here directly in README.md using [markdown](https://guides.github.com/features/mastering-markdown/) and linking to the specific exercise pages, below is an example.

- [Getting Started](exercises/ex0/)
- [Exercise 1 - First Exercise Description](exercises/ex1/)
    - [Exercise 1.1 - Exercise 1 Sub Exercise 1 Description](exercises/ex1#exercise-11-sub-exercise-1-description)
    - [Exercise 1.2 - Exercise 1 Sub Exercise 2 Description](exercises/ex1#exercise-12-sub-exercise-2-description)
- [Exercise 2 - Second Exercise Description](exercises/ex2/)
    - [Exercise 2.1 - Exercise 2 Sub Exercise 1 Description](exercises/ex2#exercise-21-sub-exercise-1-description)
    - [Exercise 2.2 - Exercise 2 Sub Exercise 2 Description](exercises/ex2#exercise-22-sub-exercise-2-description)

  
**OR** Link to the Tutorial Navigator for example...

Start the exercises [here](https://developers.sap.com/tutorials/abap-environment-trial-onboarding.html).

**IMPORTANT**

Your repo must contain the .reuse and LICENSES folder and the License section below. DO NOT REMOVE the section or folders/files. Also, remove all unused template assets(images, folders, etc) from the exercises folder. 

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright (c) 2022 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
