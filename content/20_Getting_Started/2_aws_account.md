+++
title = "AWS Account"
chapter = false
weight = 2
+++

{{% notice warning %}}
You are responsible for the cost of the AWS services used while running this workshop in your AWS account.
{{% /notice %}}

{{% notice warning %}}
Your account must have the ability to create new IAM roles and scope other IAM permissions.
{{% /notice %}}


### Create an account 

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
   	  <td class="med-number-bold">1.</td>
   	  <td class="sm-text-bold">If you don't already have an AWS account with Administrator access: <a href="http://docs.aws.amazon.com/connect/latest/adminguide/gettingstarted.html#sign-up-for-aws" target="_blank">create one now</a></td>
   </tr>
</table>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
   	  <td class="med-number-bold">2.</td>
   	  <td class="sm-text-bold">Once you have an AWS account, ensure you are following the remaining workshop steps as an IAM user with administrator access to the AWS account: <a href="https://console.aws.amazon.com/iam/home?region=us-east-1#/users$new" target="_blank">Create a new IAM user to use for the workshop</a></td>
   </tr>
</table>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
   	  <td class="med-number-bold">3.</td>
   	  <td class="sm-text-bold">Enter the user details:</td>
   </tr>
</table>
![Create User](/images/20_Getting_Started/iam-1-create-user.png)

<br>
<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
   	  <td class="med-number-bold">4.</td>
   	  <td class="sm-text-bold">Attach the AdministratorAccess IAM Policy:</td>
   </tr>
</table>
![Attach Policy](/images/20_Getting_Started/iam-2-attach-policy.png)
<br>
<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
   	  <td class="med-number-bold">5.</td>
   	  <td class="sm-text-bold">Click to create the new user:</td>
   </tr>
</table>
![Confirm User](/images/20_Getting_Started/iam-3-create-user.png)
<br>
<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
   	  <td class="med-number-bold">6.</td>
   	  <td class="sm-text-bold">Take note of the login URL and save:</td>
   </tr>
</table>
![Login URL](/images/20_Getting_Started/iam-4-save-url.png)

<!--
<span class="small-text">**1 .** &nbsp; If you don't already have an AWS account with Administrator access: <a href="http://docs.aws.amazon.com/connect/latest/adminguide/gettingstarted.html#sign-up-for-aws" target="_blank">**create one now**</a></span>

<span class="small-text">**2 .** &nbsp; Once you have an AWS account, ensure you are following the remaining workshop steps
as an **IAM user** with administrator access to the AWS account: <a href="https://console.aws.amazon.com/iam/home?region=us-east-1#/users$new" target="_blank">**Create a new IAM user to use for the workshop**</a></span>

<span class="small-text">**3 .** &nbsp; Enter the user details:</span>
![Create User](/images/20_Getting_Started/iam-1-create-user.png)

<span class="small-text">**4 .** &nbsp; Attach the AdministratorAccess IAM Policy:</span>
![Attach Policy](/images/20_Getting_Started/iam-2-attach-policy.png)

<span class="small-text">**5 .** &nbsp; Click to create the new user:</span>
![Confirm User](/images/20_Getting_Started/iam-3-create-user.png)

<span class="small-text">**6 .** &nbsp; Take note of the login URL and save:</span>
![Login URL](/images/20_Getting_Started/iam-4-save-url.png)

-->