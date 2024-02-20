+++
title = "Run Setup Utility"
chapter = false
weight = 5
+++

![image](/images/30_Workshop_Setup/ad_team_tech_lead.png)

{{% notice warning %}}
You must **have enough available VPCs, Elastic IPs, and NAT Gatewways in the region you are working in** to successfully **create an EKS Cluster** with a managed node group of 2 nodes.  You also need to have space for three S3 Buckets. If you **run into a problem** during the setup, it is **usually associated with insufficient resources or permissions in your AWS account**.  You can resolve resource constraints by <a href="https://docs.aws.amazon.com/servicequotas/latest/userguide/request-quota-increase.html" target="_blank">**requesting a quota increase**</a> for your AWS account.
{{% /notice %}}

{{% notice warning %}}
In order to prevent charges to your AWS account, we recommend cleaning up the infrastructure that gets created with the setup utility. If you plan to keep things running so you can examine the workshop a bit more, please remember to do the cleanup when you are done. It is very easy to leave things running in an AWS account, forget about it, and then accrue charges.
{{% /notice %}}


{{% notice info %}}
Just so you understand ahead of time, you can easily clean up all the resources that get created by the setup utility by using the commands below: <br><br>
**cd /home/ec2-user/environment** <br>
**./teardownWorkshop.sh**
{{% /notice %}}

### Let's do this ! <span style="color: #3e3071;"><i class='fas fa-cog fa-sm fa-spin'></i></span>


<span class="small-text">Now that you've got all the prerequisites out of the way, you can kick off the initial setup steps and go grab a cup of coffee <i class='fas fa-coffee'></i> while the setup utility runs.</span>

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Ensure you are in your home directory by executing the command below:</td>
   </tr>
</table>

```
cd /home/ec2-user/environment
```

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Clone the workshop repository by using the following command:</td>
   </tr>
</table>

```
git clone https://github.com/APO-SRE/appd_aws_migration_lab.git migration_workshop
```

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">After the workshop repository is cloned, use the following command to change to the cloned repository directory:</td>
   </tr>
</table>

```
cd migration_workshop
```

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Use the following command to make the script executable:</td>
   </tr>
</table>

```
chmod +x setup_workshop.sh
```

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Use five (5) letters of your first, and or, your last name to create your unique workshop user name using the command below:</td>
   </tr>
</table>


<span class="small-text"><strong>EXAMPLE:</strong>&nbsp; export appd_workshop_user=TOMSM</span>

```
export appd_workshop_user=<YOUR USER NAME>
```

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Use the command below to execute the setup script:</td>
   </tr>
</table>

```
./setup_workshop.sh
```


{{% notice info %}}
<span><i class='fas fa-hourglass-half fa-lg'></i></span> The setup utility first attempts to increase the size of the EBS volume or disk size.  The 'aws ec2 modify-volume' service is frequently unavailable so this script is set to retry 100 times to connect to the service. Be prepared **to wait up to 20 minutes or more for the volume resizing** to complete because of the intermittent reliability of this AWS service. You can safley stop this script from running if desired and rerun it at a later time as well. After the volume is resized, the remaining tasks of setup utility take **approximately 22 minutes to complete**. <span><i class='fas fa-hourglass-half fa-lg'></i></span>
{{% /notice %}}


<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">The output from the start of the setup script should look like this:</td>
   </tr>
</table>


![image](/images/30_Workshop_Setup/setup-output-start.png)

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">The output from the setup script when it ends, should look like this:</td>
   </tr>
</table>


![image](/images/30_Workshop_Setup/setup-output-end.png)


### What the setup utility does

**01)** Resizes the Disk on your Cloud9 instance <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**02)** Installs Java JDK 1.8 <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**03)** Installs kubectl <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**04)** Installs eksctl <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**05)** Installs Helm <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**06)** Installs AWS EC2 Meta-Data Utilities <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**07)** Installs docker-compose <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**08)** Installs MariaDB <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**09)** Installs MongoDB <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**10)** Installs the AppDynamics Database agent <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**11)** Installs the AppDynamics Server Monitoring agent <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**12)** Creates an EC2 security group for external access to RDS Databases <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**13)** Creates RDS databases with the security group attached <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**14)** Creates three S3 buckets <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**15)** Creates two Application Performance Monitoring apps in the AppDynamics Controller <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**16)** Creates two Browser Real User Monitoring apps in the AppDynamics Controller <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**17)** Creates two AppDynamics Database collectors in the AppDynamics Controller <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**18)** Creates an RBAC User in the AppDynamics Controller <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**19)** Creates an RBAC Role in the AppDynamics Controller <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**20)** Adds the RBAC User in the AppDynamics Controller to the appropriate RBAC Roles <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**21)** Deploys the Pre-Migration application to your local C9 instance <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

**23)** Creates the teardown file <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>


Using a shell script - <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

Using the AWS Java SDK - <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>

Using the AppDynamics REST API - <span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span><span style="color: #3e3071;"><i class='fas fa-asterisk fa-xs'></i></span>


### Additional setup in following sections

<span class="small-text">There will be some additional setup steps in the following sections listed below.  There's no need to do them now.  Wait until you've reached those sections to perform the steps for each section.</span>

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-circle fa-xs'></i></td>
      <td class="sm-text">Migration Phase Section</td>
   </tr>
</table>

<table class="table-with-line-and-wrapped-text">
   <tr class="main-row">
      <td class="sm-line"><i style="color: #3e3071;" class='fas fa-minus fa-xs'></i></td>
      <td class="sm-text">Create the EKS Cluster</td>
   </tr>
   <tr class="main-row">
      <td class="sm-line"><i style="color: #3e3071;" class='fas fa-minus fa-xs'></i></td>
      <td class="sm-text">Deploy the Application to EKS</td>
   </tr>
   <tr class="main-row">
      <td class="sm-line"><i style="color: #3e3071;" class='fas fa-minus fa-xs'></i></td>
      <td class="sm-text">Deploy the AppDynamics Helm Chart to EKS</td>
   </tr>

</table>


### What the final architecture will look like

![image](/images/30_Workshop_Setup/arch_diagram.png)


### [**Next**]({{< ref "40_Cloud_Migration" >}}) <span style="color: #3e3071;"><i class='fas fa-cog fa-sm fa-spin'></i></span>

<span class="small-text">**While we are waiting** for the setup utility to finish, **let's dive into the Cloud Migration section**.</span>

