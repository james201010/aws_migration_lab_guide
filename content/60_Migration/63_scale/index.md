+++
title = "Scale"
chapter = false
weight = 3
hidden = false
+++


![image](/images/60_Migration/ad_team_developer.png)

<hr class="xsmall-line"> 

### Remote Services - S3

In addition to the flow map reflecting all of the changes in the real time topology of the application, we can view Remote Services to show the detailed metrics of the calls to the new secure storage solution, S3. 

**1 .**  Click on **Remote Services** on the left menu.

**2 .**  Notice the sub-second response time for all the S3 calls.

You can read more about Remote Services <a href="https://docs.appdynamics.com/appd/23.x/latest/en/application-monitoring/remote-services" target="_blank">**here**</a>

![image](/images/60_Migration/remote_services_00.png)

<br>

### Databases - RDS

The native MySQL database used in the pre-migrated version of the application was straining to keep up with the demand of the application load.  Let's take a look at how much better the new AWS RDS MySQL database is performing.

**1 .**  Navigate to the database named like **adfin-post-migrate-&lt;your_lab_user_name&gt;-mysql**

**2 .**  Click on the colored health status circle to see details of the server health

**3 .**  Observe the total time spent executing SQL statements during the specified time period

**4 .**  Observe the total number of executions during the specified time period

**5 .**  Hover over the time series on the chart to see the detail of the recorded metrics

**6 .**  Hover over the labels for each wait state to see a more detailed description

![image](/images/60_Migration/databases_00.png)


### Here's the Advantage

- Easily compare and validate the throughput and resource usage of the hosts and containers in the application
- Quickly observe the availability and performance of the cloud services within the application context
- Understand database performance in detail to validate improvements after migrating to RDS


### [**Next**]({{< ref "64_business_iq" >}}) <span style="color: #3e3071;"><i class='fas fa-cog fa-spin'></i></span>

In the next section we'll examine how AppDynamics **Business iQ** provides **deep visibility into key real-time business metrics** correlated to application performance.


<!---
{{% notice warning %}}
The Cloud9 workspace should be built by an IAM user with Administrator privileges,
not the root account user. Please ensure you are logged in as an IAM user, not the root
account user.
{{% /notice %}}
-->

<!---
{{% notice info %}}
This workshop was designed to run in the **Oregon (us-west-2)** region. **Please don't
run in any other region.** Future versions of this workshop will expand region availability,
and this message will be removed.
{{% /notice %}}
-->

<!---
{{% notice tip %}}
Ad blockers, javascript disablers, and tracking blockers should be disabled for
the cloud9 domain, or connecting to the workspace might be impacted.
Cloud9 requires third-party-cookies. You can whitelist the [specific domains]( https://docs.aws.amazon.com/cloud9/latest/user-guide/troubleshooting.html#troubleshooting-env-loading).
{{% /notice %}}
-->
