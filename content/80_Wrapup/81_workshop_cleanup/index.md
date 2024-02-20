+++
title = "Workshop Cleanup"
chapter = false
weight = 1
+++

<br>

### Congratulations! &nbsp;&nbsp; You have successfully completed the Migration Workshop with Cisco Appdynamics! &nbsp;&nbsp; 


<br>

{{% notice warning %}}
In order to prevent charges to your AWS account, we recommend cleaning up the infrastructure that was created. If you plan to keep things running so you can examine the workshop a bit more, please remember to do the cleanup when you are done. It is very easy to leave things running in an AWS account, forget about it, and then accrue charges.
{{% /notice %}}

<span style="color: #3e3071;"><i class='fas fa-circle fa-sm'></i></span> Execute the commands below to cleanup all workshop resources:

```
cd /home/ec2-user/environment/migration_workshop/

./teardown_workshop.sh 
```

{{% notice info %}}
The setup utility takes approximately 10 minutes to complete.
{{% /notice %}}

<span style="color: #3e3071;"><i class='fas fa-circle fa-sm'></i></span> The output from the teardown script when it starts, should look like this:

![image](/images/80_Wrapup/teardown_start.png)


<span style="color: #3e3071;"><i class='fas fa-circle fa-sm'></i></span> The output from the teardown script when it deletes the EKS cluster, should look like this:

![image](/images/80_Wrapup/teardown_middle.png)


<span style="color: #3e3071;"><i class='fas fa-circle fa-sm'></i></span> The output from the teardown script when it ends, should look like this:

![image](/images/80_Wrapup/teardown_end.png)

### [**Next**]({{< ref "82_cloud9_cleanup" >}}) <span style="color: #3e3071;"><i class='fas fa-cog fa-spin'></i></span>

We'll walk through the **steps to cleanup the Cloud9 instance** you created for the workshop.
