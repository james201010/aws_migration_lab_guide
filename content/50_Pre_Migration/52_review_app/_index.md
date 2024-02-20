+++
title = "Explore the Monolithic App"
chapter = false
weight = 2
hidden = true
+++

![image](/images/50_Pre_Migration/ad_team_architect.png)

<hr class="xsmall-line">

### AD Financial Monolithic Application

<span class="medium-text">Before we login to the AppDynamics console to observe the pre-migration version of the application, let’s take a quick look at the web interface of the application from an end users perspective.</span>

<span class="medium-text">Use the following steps to find the URL to the web site:</span>


<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">1.</td>
      <td class="sm-text">Go to your Cloud9 console and click on the <span class="small-text-bold">Preview</span> option at the top</td>
   </tr>
</table>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">2.</td>
      <td class="sm-text">Then select <span class="small-text-bold">Preview Running Application</span> from the drop down</td>
   </tr>
</table>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">3.</td>
      <td class="sm-text">If the web home page doesn’t show up, you may need to click in the address bar and add <span class="small-text-bold">:8080</span> after <span class="small-text-bold">amazonaws.com</span> at the end of the URL and hit enter</td>
   </tr>
</table>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">4.</td>
      <td class="sm-text">Now click on the button <span class="small-text-bold">to the right of the “Browser” button</span> to open the web page in a new browser tab</td>
   </tr>
</table>

{{% notice info %}}
If the web page doesn't come up then try using a different browser. Chrome usually works the best.
{{% /notice %}}

![image](/images/50_Pre_Migration/find_web_url_01.png)

<br>

### Login to the Monolithic Web Site

<span class="medium-text">Use the following steps to login to the web site:</span>


<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">1.</td>
      <td class="sm-text">Type in <span class="small-text-bold">batman</span> for the online id / user name</td>
   </tr>
</table>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">2.</td>
      <td class="sm-text">Type in any password of your choosing</td>
   </tr>
</table>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">3.</td>
      <td class="sm-text">Click on the <span class="small-text-bold">Sign In</span> button to login</td>
   </tr>
</table>

![image](/images/50_Pre_Migration/web_site_01.png)


<span class="medium-text">Now that you are logged in, you should see the different accounts for the user:</span>

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Personal Checking</td>
   </tr>
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Personal Savings</td>
   </tr>
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Auto Loan</td>
   </tr>
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Home Loan</td>
   </tr>
</table>


![image](/images/50_Pre_Migration/web_site_02.png)

<span class="medium-text">Click on any of the four accounts to see the transaction history. You can click on the <span class="small-text-bold">Accounts</span> tab on the top menu to navigate back to the accounts summary screen.</span>


![image](/images/50_Pre_Migration/web_site_03.png)


### [**Next**]({{< ref "53_appd_login" >}}) <span style="color: #3e3071;"><i class='fas fa-cog fa-spin'></i></span>

<span class="small-text">We’ll walk through the login process for the AppDynamics Controller that you’ll be using throughout the workshop.</span>
