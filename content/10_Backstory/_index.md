+++
title = "Backstory"
chapter = false
weight = 10
+++

![image](/images/10_Backstory/ad_financial_logo_lrg.png)

<span class="large-text">AD Financial serves its customers with a full range of financial products and services through award-winning digital banking capabilities and a retail banking network across the globe with a focus on helping individuals navigate each stage of their financial lives, working with  large and small businesses to drive their success by providing award-winning service.</span>

![image](/images/10_Backstory/ad_financial_web.png)

<!--
AD Financial recently experienced a data breach in their online application, and while the breach was minimized, the source of the breach was never determined due to lack of granularity in the stored audit data.  The need for a replicated audit trail, containing more details of how the data was accessed, became immediately apparent.  The ingestion of audit data combined with loan application updates within the same DB instance could also be negatively impacting database performance. -->

### **Introduction**

<span class="small-text">AD Financial has experienced a surge in demand for home mortgage refinancing and small business loans over the past six months.  As a result, their web site and the backend services that support it have suffered from slower loan processing times and downtimes while customer service has seen a rise in complaints from end users.  There has been significant loss in revenue due to frequent downtimes and longer time to recover.</span>  

<span class="small-text">AD Financial fully intends to maintain its brand and position in the competitive financial market. The budget has been approved to proceed with the migration project that will help the company retain its competitive edge and customer loyaly.  An initial assessment of the current web site and the loan processing services behind it revealed several areas that warrant further analysis.</span>

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Recent changes to the UI framework on the web site need review</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Backend service FinancialServices has too many loan service functionalities tightly coupled, e.g. personal loan, business loan, etc</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Collocation of loan data and audit data may be constraining the database</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Current Monolithic architecture lacks scalability features</td>
   </tr>
</table>

<br>

<span class="small-text">Avi is the Chief Technology Officer (CTO) for AD Financial and has tasked his team leads to assess the following challenges associated with the migration effort:</span>

![image](/images/10_Backstory/ad_team_cto.png)



### **1. Understand the Current Application**

<span class="small-text">It has been over a year since the Dev team refactored the online application and  Infra team assessed the capacity of supporting infrastructure in the data center.  There is no current architecture diagram for the application and many changes have been made since its original deployment. An accurate assessment of the items below are required so the team can create a viable migration plan:</span>


<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Differentiate issues in the web UI versus the backend services</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Inventory of all application hosts and their resource utilization</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Inventory of all Database hosts and their resource utilization</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Core Business logic design and their interdependencies</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Inventory of all dependencies to backends and third-party systems</td>
   </tr>
</table>


<!--
&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Differentiate issues in the web UI versus the backend services**</span>

&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Inventory of all application hosts and their resource utilization**</span>

&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Inventory of all Database hosts and their resource utilization**</span>

&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Core Business logic design and their interdependencies**</span>

&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Inventory of all dependencies to backends and third-party systems**</span>
-->


### **2. Understand Key Business Transactions**

<span class="small-text">Once we have an inventory of the application components, services, and dependencies, we need to understand what the key business transactions are in the application and the components they map to so we can prioritize them for refactoring during our migration effort.  For example, what are the transactions that access sensitive data and require auditing?  What are the key business transactions associated with services we want to refactor? To answer those questions, we need to understand the following:</span>



<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">What are the transactions associated with loan processing that would be effected when decoupling services?</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">The path those transactions take through the system with all components involved to map them out from start to finish.</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">What specific components are causing performance degradation of key business transactions:</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Core Business logic design and their interdependencies</td>
   </tr>
</table>

<table class="table-with-line-and-wrapped-text">
   <tr class="main-row">
   	  <td class="sm-line"><i style="color: #3e3071;" class='fas fa-minus fa-xs'></i></td>
   	  <td class="sm-text">Web page issues?</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-line"><i style="color: #3e3071;" class='fas fa-minus fa-xs'></i></td>
   	  <td class="sm-text">Code related issues?</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-line"><i style="color: #3e3071;" class='fas fa-minus fa-xs'></i></td>
   	  <td class="sm-text">Database constraints?</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-line"><i style="color: #3e3071;" class='fas fa-minus fa-xs'></i></td>
   	  <td class="sm-text">Infrastructure constraints?</td>
   </tr>
</table>



<!--
&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**What are the transactions associated with loan processing that would be effected when decoupling services?**</span>

&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**The path those transactions take through the system with all components involved to map them out from start to finish.**</span>

&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**What specific components are causing performance degradation of key business transactions:**</span>



&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-minus fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Web page issues?**</span>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-minus fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Code related issues?**</span>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-minus fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Database constraints?**</span>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-minus fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Infrastructure constraints?**</span>
-->





### **3. Select the Appropriate Migration Strategy**

<span class="small-text">The landscape of new cloud services and technologies available today have made dramatic improvements in efficiency in recent years.  However, the services and technologies selected and adopted need to satisfy the business and engineering requirements while also promoting adoption across the different teams involved in the migration effort.</span>

<span class="small-text">To that end, the business:</span>


<!--
&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Anticipates the need to scale and operate more efficiently due to growing demand and higher transaction rates**</span>

&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Looks to separate the storage and access of audit data to increase throughput and scale them independently**</span>

&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Adopt microservice architecture for FinancialServices core business logic which is tightly coupled by breaking them down into smaller units\services making them highly available & scalable and eliminating any single point of failures**</span>

&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Must reduce or eliminate downtime and service outages due to competing demands of reporting and loan submissions**</span>
-->

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Anticipates the need to scale and operate more efficiently due to growing demand and higher transaction rates</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Looks to separate the storage and access of audit data to increase throughput and scale them independently</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Adopt microservice architecture for FinancialServices core business logic which is tightly coupled by breaking them down into smaller units\services making them highly available & scalable and eliminating any single point of failures</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Must reduce or eliminate downtime and service outages due to competing demands of reporting and loan submissions</td>
   </tr>
</table>	



### **4. Validate Performance and End User Experience**

<span class="small-text">Validating the success of our migration effort will be next to impossible without having an accurate understanding of what the application and business performance metrics are, as well as end user experience metrics, both pre-migration and post-migration.  Our CTO Avi, has recommended that we capture baseline data on the following indicators for the application, both pre and post migration to validate our success:</span>


<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Overall end user experience online</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Business transaction performance</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Component and service level performance</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Business performance of the loan approval process</td>
   </tr>
</table>	



<!--

&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Overall end user experience online**</span>

&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Business transaction performance**</span>

&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Component and service level performance**</span>

&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Business performance of the loan approval process**</span>

-->

<!-- Consolidating metrics from the siloed tools used by the teams at various layers of the application takes too much time and effort and doesn’t scale well.  The current tools have no way of providing an end to end view of the entire application stack in its current form, nor would they give any visibility into the native cloud services like S3 and EKS.  Current tools also lack any capability of automatic baselines for performance and end user experience, at the application, business transaction, service, and component level. -->

### **5. Streamline Operations &#38; Minimize Risk**

<span class="small-text">The challenges associated with large modernized enterprise applications in a virtual and dynamic cloud landscape can be complex. This is especially true for the operations team that manage those production applications.  Now they must support applications that utilize new cloud services and technologies they may not be familiar with.  The operations team recognizes that they need to realign their strategy and operational toolset to perform efficiently and effectively while staying within their budget.</span>

<span class="small-text">Specifically, how can the operations team:</span>

<table class="table-with-icon-and-wrapped-text">
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Be proactively alerted to pinpoint root cause before it affects the end user or impacts the business?</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Get deep visibility into the new cloud native services being utilized by the application?</td>
   </tr>
   <tr class="main-row">
   	  <td class="sm-icon"><i style="color: #3e3071;" class='fas fa-certificate fa-xs'></i></td>
   	  <td class="sm-text">Keep performing optimally while supporting new technologies without growing the size of the team?</td>
   </tr>
</table>

<!--
&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Be proactively alerted to pinpoint root cause before it affects the end user or impacts the business?**</span>

&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Get deep visibility into the new cloud native services being utilized by the application?**</span>

&nbsp;&nbsp;&nbsp;<span style="color: #3e3071;"><i class='fas fa-certificate fa-xs'></i></span>&nbsp; <span style="font-size:11.5pt">**Keep performing optimally while supporting new technologies without growing the size of the team?**</span>
-->



<br>

### [**Next**]({{< ref "20_Getting_Started" >}}) <span style="color: #3e3071;"><i class='fas fa-cog fa-sm fa-spin'></i></span>

<span class="small-text">Let's get started by **setting up the prerequisites** in your **AWS environment**.</span>


<!-- **Distributed Architectures:** Microservices, containers, Kubernetes and the use of multiple AWS Availability Zones have created a more expansive and richer IT landscape.

- **Additional Dependencies:** APIs that connect to third-party services outside of the organization may not always perform as expected. The customer does not care who is at fault, they simply want a frictionless engagement with the applications.

- **Faster Release Cycles:** Release frequencies have shifted - to monthly, weekly, daily, or even hourly deployments. No matter how minor some releases may seem, they all have the potential to impact the customer experience.

Historically, monitoring has reflected the departmental nature of Development and IT Operations teams, who each used a tool for their area of responsibility, such as:

- Network
- Database
- Web
- Mobile
- Server

Proliferation of these tools has often led to:

- **Finger Pointing:** More time spent proving innocence vs. collaborating, results in slower Root Cause Analysis (RCA) and poor team collaboration.

- **Lack of Visibility:** No insight into end-to-end execution times, which causes “watermelon KPIs,” i.e. looks green, but users still struggle.

- **Suboptimal Prioritization:** Teams are unaware of the true business impact of what has occurred. 


The operations team needs to keep their end users happy and maximize revenue. AppDynamics helps ensure optimal user experience by measuring key performance metrics and reporting on any deviations in real-time. However, AppDynamics goes beyond alerts by pinpointing where an issue is occurring and providing AI-driven remediation recommendations. This capability is especially important to proactively identify potential issues before they result in degraded customer experiences and potential lost business.  
-->