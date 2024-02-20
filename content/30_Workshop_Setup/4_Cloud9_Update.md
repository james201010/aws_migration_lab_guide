+++
title = "Update Cloud9 Workspace"
chapter = false
weight = 4
+++

![image](/images/30_Workshop_Setup/ad_team_tech_lead.png)

### Turn Off Managed Credentials

{{% notice info %}}
**Cloud9 manages IAM credentials** with **temporary credentials by default**. **This is not currently compatible with the EKS IAM authentication**, so **we must disable it and rely on the IAM role we just created** instead.
{{% /notice %}}

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Return to your workspace and click the gear icon (in top right corner), or click to open a new tab and choose <strong>Open Preferences</strong></td>
   </tr>
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Select <strong>AWS Settings</strong></td>
   </tr>
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Turn <strong>OFF AWS managed temporary credentials</strong></td>
   </tr>
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Close the Preferences tab</td>
   </tr>
</table>

![c9configure](/images/30_Workshop_Setup/c9_configure_02.png)


### Validate the IAM Role

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Use the <a href="https://docs.aws.amazon.com/cli/latest/reference/sts/get-caller-identity.html" target="_blank"><strong>GetCallerIdentity</strong></a> CLI command to validate that the Cloud9 IDE is using the correct IAM role.</td>
   </tr>
</table>

```
aws sts get-caller-identity --query Arn | grep AppD-Workshop-Admin -q && echo "IAM role valid" || echo "IAM role NOT valid"
```

{{% notice warning %}}
**If the IAM role is not valid, DO NOT PROCEED**. Go back and confirm the steps on this page.
{{% /notice %}}


### [**Next**]({{< ref "5_Run_Setup" >}}) <span style="color: #3e3071;"><i class='fas fa-cog fa-sm fa-spin'></i></span>