+++
title = "Create Cloud9 Workspace"
chapter = false
weight = 1
+++

![image](/images/30_Workshop_Setup/ad_team_tech_lead.png)

{{% notice warning %}}
The Cloud9 workspace should be built by an IAM user with Administrator privileges,
not the root account user. Please ensure you are logged in as an IAM user, not the root
account user.
{{% /notice %}}

<!---
{{% notice info %}}
This workshop was designed to run in the **Oregon (us-west-2)** region. **Please don't
run in any other region.** Future versions of this workshop will expand region availability,
and this message will be removed.
{{% /notice %}}
-->

{{% notice tip %}}
Ad blockers, javascript disablers, and tracking blockers should be disabled for
the cloud9 domain, or connecting to the workspace might be impacted.
Cloud9 requires third-party-cookies. You can whitelist the <a href="https://docs.aws.amazon.com/cloud9/latest/user-guide/troubleshooting.html#troubleshooting-env-loading" target="_blank">**specific domains**</a>.
{{% /notice %}}


### Launch Cloud9 in your closest region

Use a single region for the duration of this workshop. This workshop supports the following regions, however:

{{% notice info %}}
If you are using the **Events Engine please be aware** that there are **only two regions suported**. They are **N. California - us-west-1** and **Oregon - us-west-2**
{{% /notice %}}

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">N. California</td>
   </tr>
</table>
<table class="table-with-line-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-line"><i style="color: #3e3071;" class='fas fa-minus fa-xs'></i></td>
      <td class="sm-text"><a href="https://us-west-1.console.aws.amazon.com/cloud9/home?region=us-west-1" target="_blank">us-west-1</a></td>
   </tr>
</table>

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Oregon</td>
   </tr>
</table>
<table class="table-with-line-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-line"><i style="color: #3e3071;" class='fas fa-minus fa-xs'></i></td>
      <td class="sm-text"><a href="https://us-west-2.console.aws.amazon.com/cloud9/home?region=us-west-2" target="_blank">us-west-2</a></td>
   </tr>
</table>

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">N. Virginia</td>
   </tr>
</table>
<table class="table-with-line-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-line"><i style="color: #3e3071;" class='fas fa-minus fa-xs'></i></td>
      <td class="sm-text"><a href="https://us-east-1.console.aws.amazon.com/cloud9/home?region=us-east-1" target="_blank">us-east-1</a></td>
   </tr>
</table>

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Ohio</td>
   </tr>
</table>
<table class="table-with-line-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-line"><i style="color: #3e3071;" class='fas fa-minus fa-xs'></i></td>
      <td class="sm-text"><a href="https://us-east-2.console.aws.amazon.com/cloud9/home?region=us-east-2" target="_blank">us-east-2</a></td>
   </tr>
</table>

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Ireland</td>
   </tr>
</table>
<table class="table-with-line-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-line"><i style="color: #3e3071;" class='fas fa-minus fa-xs'></i></td>
      <td class="sm-text"><a href="https://eu-west-1.console.aws.amazon.com/cloud9/home?region=eu-west-1" target="_blank">eu-west-1</a></td>
   </tr>
</table>

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Singapore</td>
   </tr>
</table>
<table class="table-with-line-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-line"><i style="color: #3e3071;" class='fas fa-minus fa-xs'></i></td>
      <td class="sm-text"><a href="https://ap-southeast-1.console.aws.amazon.com/cloud9/home?region=ap-southeast-1" target="_blank">ap-southeast-1</a></td>
   </tr>
</table>



{{% notice warning %}}
You **must use** the **t3.large** instance type for this workshop.  If the **t3.large** instance type is not available in the region you first selected, please choose a different region where the **t3.large** instance type is available.
{{% /notice %}}

{{% notice warning %}}
You **must use** the **Amazon Linux 2** platform type for this workshop.  If the **Amazon Linux 2** platform type is not available in the region you first selected, please choose a different region where the **Amazon Linux 2** platform type is available.
{{% /notice %}}

### Select your options

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Select <strong>Create environment</strong></td>
   </tr>
</table>

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Name it <strong>AppD-Migration-Workshop</strong>, click Next.</td>
   </tr>
</table>

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Choose <strong>t3.large</strong> for instance type, ensure <strong>Amazon Linux 2</strong> is selcted as the platform, choose <strong>After four hours</strong> for cost saving setting, as seen below.</td>
   </tr>
</table>


![c9configure](/images/30_Workshop_Setup/c9_configure_01.png)

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Click <strong>Next Step</strong>, then click <strong>Create environment</strong></td>
   </tr>
</table>

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">When it comes up, customize the environment by closing the <strong>welcome tab</strong> and <strong>lower work area</strong>, and opening a new <strong>terminal</strong> tab in the main work area:</td>
   </tr>
</table> 

![c9before](/images/30_Workshop_Setup/c9_before.png)


<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Your workspace should now look like this:</td>
   </tr>
</table> 

![c9after](/images/30_Workshop_Setup/c9_after.png)

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">If you like this theme, you can choose it yourself by selecting <strong>View / Themes / Solarized / Solarized Dark</strong>
in the Cloud9 workspace menu.</td>
   </tr>
</table> 



<br>

### [**Next**]({{< ref "2_Create_IAM_Role" >}}) <span style="color: #3e3071;"><i class='fas fa-cog fa-sm fa-spin'></i></span>

