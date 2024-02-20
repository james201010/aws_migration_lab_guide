+++
title = "Workshop Setup"
chapter = false
weight = 30
+++

<span class="large-text">Zoe is the Technical Lead for the migration project at AD Financial. &nbsp; She will walk you through the steps to get the workshop setup completed.  Please review the steps below and associated <span style="color: #3e3071;"><i class='fas fa-bolt'></i></span> notes to ensure a smooth setup.</span>


![image](/images/30_Workshop_Setup/ad_team_tech_lead.png)


<span class="large-text">Below are the workshop setup steps you will need to complete:</span>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">1.</td>
      <td class="sm-text-bold">Create your Cloud9 Workspace</td>
   </tr>
</table>
<span class="small-text">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-bolt'></i></span> You **must use** the **t3.large** instance type when creating your Cloud9 instance</span>

<span class="small-text">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-bolt'></i></span> You **must select** the platform **Amazon Linux 2** when creating your Cloud9 instance</span>


<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">2.</td>
      <td class="sm-text-bold">Create an IAM Role for your Cloud9 Workspace</td>
   </tr>
</table>
<span class="small-text">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-bolt'></i></span> You **must create** the IAM Role with **AdministratorAccess**</span>


<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">3.</td>
      <td class="sm-text-bold">Attach the IAM Role to your Cloud9 Workspace</td>
   </tr>
</table>
<span class="small-text">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-bolt'></i></span> You **must attach** the IAM Role with **AdministratorAccess** to your Cloud9 instance</span>



<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">4.</td>
      <td class="sm-text-bold">Update your Cloud9 Workspace</td>
   </tr>
</table>
<span class="small-text">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-bolt'></i></span> You **must turn OFF** AWS managed temporary credentials</span>



<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">5.</td>
      <td class="sm-text-bold">Start Your Engines !</td>
   </tr>
</table>
<span class="small-text">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-bolt'></i></span> You **must check** for **available EKS resources** before you start racing to the finish line</span>


<!--
#### &nbsp; **1 .** &nbsp; Create your Cloud9 Workspace

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-bolt'></i></span> You **must use** the **t3.large** instance type when creating your Cloud9 instance

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-bolt'></i></span> You **must select** the platform **Amazon Linux 2** when creating your Cloud9 instance

#### &nbsp; **2 .** &nbsp; Create an IAM Role for your Cloud9 Workspace

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-bolt'></i></span> You **must create** the IAM Role with **AdministratorAccess**

#### &nbsp; **3 .** &nbsp; Attach the IAM Role to your Cloud9 Workspace

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-bolt'></i></span> You **must attach** the IAM Role with **AdministratorAccess** to your Cloud9 instance

#### &nbsp; **4 .** &nbsp; Update your Cloud9 Workspace

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-bolt'></i></span> You **must turn OFF** AWS managed temporary credentials



#### &nbsp; **5 .** &nbsp; Start Your Engines !

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-bolt'></i></span> You **must check** for **available EKS resources** before you start racing to the finish line 

-->

<br>

### [**Next**]({{< ref "1_Create_Cloud9" >}}) <span style="color: #3e3071;"><i class='fas fa-cog fa-sm fa-spin'></i></span>


