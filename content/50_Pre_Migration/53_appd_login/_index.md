+++
title = "Login to AppDynamics"
chapter = false
weight = 3
hidden = false
+++


![image](/images/50_Pre_Migration/ad_team_architect.png)

<hr class="xsmall-line">

### Login to the AppDynamics Controller

<span class="medium-text">Once the setup utility has finished, you can find your login credentials to your AppDynamics Controller by using the commands below:</span>

```
cd /home/ec2-user/environment/migration_workshop

cat workshop-user-details.txt
```

<span class="medium-text">Your workshop user details file should have the following information similar to the image below:</span>


- The URL to the AppDynamics Controller you will use
- The credentials you will use to login to the Controller
- The names of the Pre-Modernization APM and EUM applications
- The names of the Post-Modernization APM and EUM applications

![image](/images/50_Pre_Migration/user_details.png)

<span class="medium-text">In a separate browser tab or window, navigate to the URL that is next to Controller URL in the workshop user details file. Use the data from the workshop user details file to login to AppDynamics.</span>


{{% notice tip %}}
The account and username are two distinct fields that are used as part of logging in.
{{% /notice %}}

![image](/images/50_Pre_Migration/appd_login.png)



### [**Next**]({{< ref "54_end_user_exp" >}}) <span style="color: #3e3071;"><i class='fas fa-cog fa-spin'></i></span>

<span class="small-text">We’ll start the assessment of the pre-migrated version of the AD Financial application.</span>






