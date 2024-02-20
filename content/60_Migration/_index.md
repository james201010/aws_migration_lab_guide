+++
title = "Migration Phase"
chapter = false
weight = 60
hidden = false
+++

![image](/images/60_Migration/ad_team_developer.png)

<hr class="xsmall-line"> 

### Introduction

<span class="medium-text">Alex is the Development Lead for the modernization project at AD Financial. &nbsp; He has been be working closely with Nathan to implement the modernized application, utilizing several AWS services. &nbsp; Alex understands how using modern cloud services, including container management technologies, can accelerate the performance, deployment, and management of mission critical applications.</span>


<span class="medium-text">During the Modernization phase, Nathan and his team derived the following conclusions based on their findings:</span>

&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-sm'></i></span>&nbsp; The frontend web components were not the primary cause of high end user response times related to the loan approval process.

&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-sm'></i></span>&nbsp; Business loan processing and personal loan processing need to be separated into multiple independent services so they can be independently scaled and maintained.

&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-sm'></i></span>&nbsp; The need to have a more scalable, long-term archive storage solution for the loan audit data.  

&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-sm'></i></span>&nbsp; The collocation of loan data and audit data was constraining the database and needed to be split into independent repositories.

&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-sm'></i></span>&nbsp; The need to have monitoring intelligence down to the infrastructure layer for each component accessible within the same UI.

<br>

AWS offers multiple services for container orchestration and storage.  After careful consideration, the decision was made by the team to move forward with the following AWS stack that would best meet their technical and business requirements derived during the Mobilization phase.


&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-check-square'></i></span>&nbsp; **Container Orchestration Selection**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #efc100;"><i class='fas fa-certificate'></i></span>&nbsp; **AWS Elastic Kubernetes Service (EKS)**

&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-check-square'></i></span>&nbsp; **Storage Solution Selection**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #efc100;"><i class='fas fa-certificate'></i></span>&nbsp; **AWS Simple Storage Service (S3)**

&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-check-square'></i></span>&nbsp; **Database Solution Selection**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #efc100;"><i class='fas fa-certificate'></i></span>&nbsp; **AWS Relational Database Service (RDS)**

<br>

For container orchestration **EKS aligns well with the teams requirements**, having the ability **to automate scaling, managing, updating, and removing containers at will** without incurring any system downtime.

**S3 (Simple Storage Solution)** was chosen to host the audit data as it **provides an affordable and robust solution** to securely archive the needed audit trail while supporting high retrieval and ingestion rates with the ability to scale dynamically.

**AWS RDS was chosen** as the new database backend as it **provides the high availability and fault tolerance needed** with **real time replication across multiple availability zones and/or regions**.

![image](/images/60_Migration/app_arch_diag.png)



### [**Next**]({{< ref "61_deployment" >}}) <span style="color: #3e3071;"><i class='fas fa-cog fa-spin'></i></span>

Now it's time to **create the EKS cluster**, deploy the application to the cluster, and look at how the AppDynamics agents are configured and deployed along with the application. 
