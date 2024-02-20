+++
title = "End User Monitoring"
chapter = false
weight = 4
hidden = false
+++


![image](/images/50_Pre_Migration/ad_team_architect.png)

<hr class="xsmall-line">

### Explore the Web Front End

<span class="medium-text">The first few challanges Nathan and his team need to address are related to the web front end:</span>

- Differentiating issues in the web UI versus the backend services
- Mapping the web pages to the backend business transactions
- Baselining the end user experience on the web site with:
  - End User Response Time
  - Drop-off rates in the user journey


### Navigate to the BRUM Application

<span class="medium-text">Once you have logged into the AppDynamics controller, you should see the home page. Let's start by finding the pre-migrated version of the AD Financial BRUM (**Browser Real User Monitoring**) application and open it using the steps below.</span>


<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">1.</td>
      <td class="sm-text">Click on the <span class="small-text-bold">User Experience</span> option on the top menu.</td>
   </tr>
</table>

- In the list of **Browser Apps** you should see the application named like **adfin-pre-migrate-&lt;your_lab_user_name&gt;-web**

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">2.</td>
      <td class="sm-text">Click on the application name to open the Overview Dashboard for the application.</td>
   </tr>
</table>


![image](/images/50_Pre_Migration/open_brum_app.png)


### Browser App Dashboard

<span class="medium-text">The Browser App Overview dashboard displays a set of configurable widgets.</span>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">1.</td>
      <td class="sm-text">The dashbaord shows <span class="small-text-bold">key high-level indicators of web application performance</span>, including:</td>
   </tr>
</table>

- Page Requests per Minute
- End User Response Time Trend and Distribution
- Total Page Requests by Geo
- End User Response Time by Geo
- Top 10 Browsers and Devices
- Top 5 Pages and Countries by Total Requests

<span class="medium-text">You can read more about the Browser Application Overview dashboard <a href="https://docs.appdynamics.com/appd/23.x/latest/en/end-user-monitoring/browser-monitoring/browser-app-dashboard" target="_blank">**here**</a></span>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">2.</td>
      <td class="sm-text">Take a moment to explore the:</td>
   </tr>
</table>

- **Geo Dashboard**
  - You can read more about the Browser Application Geo dashboard <a href="https://docs.appdynamics.com/appd/23.x/latest/en/end-user-monitoring/browser-monitoring/browser-app-dashboard#BrowserAppDashboard-geo" target="_blank">**here**</a>
- **Browser Snapshots**
  - You can read more about the Browser Snapshots <a href="https://docs.appdynamics.com/appd/23.x/latest/en/end-user-monitoring/browser-monitoring/browser-app-dashboard/browser-snapshots" target="_blank">**here**</a> and <a href="https://docs.appdynamics.com/appd/23.x/latest/en/end-user-monitoring/browser-monitoring/browser-app-dashboard/browser-snapshots/page-snapshots" target="_blank">**here**</a>
- **Usage Stats**
  - You can read more about the Browser Application Usage Stats dashboard <a href="https://docs.appdynamics.com/appd/23.x/latest/en/end-user-monitoring/browser-monitoring/browser-app-dashboard#id-.BrowserAppDashboardv23.1-usagestatsUsageStats" target="_blank">**here**</a>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">3.</td>
      <td class="sm-text">Click on the <span class="small-text-bold">Pages & AJAX Requests</span> on the left to get a <span class="small-text-bold">breakdown of metrics for each web page including End User Response Time</span>.</td>
   </tr>
</table>

![image](/images/50_Pre_Migration/brum_app_01.png)


### Pages & AJAX Requests

<span class="medium-text">We want to identify the web pages that are having errors and or poor end user response times so we can focus and prioritize them if needed.</span>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">1.</td>
      <td class="sm-text">Sort the list of web pages by the highest end user response time.</td>
   </tr>
</table>

- Notice that we see **5 pages with the highest response times**, all of them **related to the loan approval process**

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">2.</td>
      <td class="sm-text">We can tell right away that the <span class="small-text-bold">high response times </span>are<span class="small-text-bold">mostly due to the First Byte Time (ms) metric</span>.</td>
   </tr>
</table>

- Though the **DOM Ready Time (ms) metric shows higher timings** than **the First Byte Time (ms) metric**, we'll explain in the next step **why the former metric is more revealing**

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">3.</td>
      <td class="sm-text">Double-click on the <span class="small-text-bold">www&#46;ad-financial&#46;com&#47;&#47;loanverifydocumentation</span> page so we can look at the detailed timing breakdown for that page.
</span>.</td>
   </tr>
</table>

![image](/images/50_Pre_Migration/brum_app_02.png)

### Base Page Dashboard

<span class="medium-text">The Base Page Dashboard shows you how a web page has been performing over time, within the context of the time range you have selected to view.</span>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">1.</td>
      <td class="sm-text">At the top of the Base Page dashboard you will see key performance indicators, End User Response Time, Load, Cache Hits, and Page Views with JS errors across the period selected in the timeframe dropdown from the upper-right side of the Controller UI. Cache Hits indicates resources fetched from a cache, such as a CDN, rather than from the source.</td>
   </tr>
</table>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">2.</td>
      <td class="sm-text">In the Timing Breakdown section you will see a waterfall graph that displays the average times needed for each aspect of the page load process. For more information on what each of the metrics measures, hover over its name on the left. A popup appears with a definition. For more detailed information, see <span class="small-text-bold"><a href="https://docs.appdynamics.com/appd/23.x/latest/en/end-user-monitoring/browser-monitoring/browser-real-user-monitoring/browser-rum-metrics" target="_blank">Browser RUM Metrics</a>.</span></td>
   </tr>
</table>

![image](/images/50_Pre_Migration/brum_app_03.png)

<span class="sm-text">The **First Byte Time metric is important** since it **tells us how much time was taken from when the page was requested, until the initial part of the response was received** from the server or backend.  This indicates that **the majority of slowness for this page is happening on the server side**.</span>

<span class="smtext">We can see in this example that **network latency was an insignificant part** of the total response time.  We can also see in the waterfall view that the **time taken to process the response after it was received and render the page was a small portion** of the total time.</span>

<span class="sm-text">You can **investigate the other 4 web pages related to the loan approval process** to validate **the majority percentage of their high end user response times is happening on the backend**.</span>



### Business Transaction Correlation

<span class="medium-text">AppDynamics automatically correlates the specific business transactions on the server side that are accessed by the Web Page and the AJAX Requests and iFrames within the page.  This valuable feature allows you to easily map out the dependencies between the frontend and the backend.</span>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">1.</td>
      <td class="sm-text">Use the scroll bar on the right to scroll down until you see the <span class="small-text-bold">Related Business Transactions</span> section.</td>
   </tr>
</table>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">2.</td>
      <td class="sm-text">We can see that this web page is accessing the <span class="small-text-bold">/rest/loanVerifyDocumentation</span> business transaction.</td>
   </tr>
</table>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">3.</td>
      <td class="sm-text">Now click on the <span class="small-text-bold">Browser Snapshots</span> tab to see individual requests for this web page.</td>
   </tr>
</table>

![image](/images/50_Pre_Migration/brum_app_04.png)



### Browser Snapshots

<span class="medium-text">AppDynamics automatically captures detailed data on each end user request to a web page as well as capturing the entire session containing the path each end user took through the web site. Here we will look at an example of a single end user page request to show you how AppDynamics automatically correlates the entire flow of an end user request.</span>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">1.</td>
      <td class="sm-text">Sort the browser snapshots on the column named <span class="small-text-bold">Has Server Snapshot</span>.</td>
   </tr>
</table>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">2.</td>
      <td class="sm-text">Double-click on the browser snapshot that has a associated server snapshot.</td>
   </tr>
</table>


![image](/images/50_Pre_Migration/brum_app_05.png)

<span class="sm-text">You can see that the browser snapshot shows the same waterfall timing breakdown and we notice once again that the majority of the time is spent waiting on the backend to fulfill the request.</span>

![image](/images/50_Pre_Migration/brum_app_06.png)

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">1.</td>
      <td class="sm-text">Use the scroll bar on the right to scroll down until you see the associated <span class="small-text-bold">Transaction Snapshot</span>.</td>
   </tr>
</table>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">2.</td>
      <td class="sm-text">Double-click on the transaction snapshot to follow the path of the user request to the backend to see why this web page request had such a high response time.</td>
   </tr>
</table>


![image](/images/50_Pre_Migration/brum_app_07.png)

<span class="sm-text">You can drill down through the entire path of the transaction with the server side transaction snapshot to quickly find root cause.  We'll explore server side transaction snapshots in more detail when we cover the upcoming section on Business Transactions.</span>

![image](/images/50_Pre_Migration/brum_app_08.png)



### Experience Journey Map

<span class="medium-text">The Experience Journey Map provides real-time insights into application and business performance, visualizing key user journeys and the correlation between performance and traffic. This perspective unifies all application stakeholders, application owners, developers, and IT operations.</span>

<table class="table-with-numbers-and-wrapped-text">
   <tr class="main-row">
      <td class="med-number-bold">1.</td>
      <td class="sm-text">Click on the <span class="small-text-bold">Experience Journey Map</span> on the left to see how <span class="small-text-bold">AppDynamics automatically maps out the journey</span> that users take through the browser application.</td>
   </tr>
</table>

<span class="sm-text">From here we can see the path of the **loan approval process** to understand:</span>

- the numer of requests for each stage and page in the process flow
- the performance of each stage and page in the process flow
- the drop-off rate from page to page in the process flow

![image](/images/50_Pre_Migration/brum_app_09.png)


### Here's the Advantage

- Identify and **take action on critical issues** with the frontend to **optimize end user experience**.
- **Aggregate and display user journeys** to **understand the most frequent paths** through the application.
- Understand the **mapping of dependencies** between **the components of the frontend and the backend business transactions they utilize**.


{{% notice info %}}
All the dashboards and the browser snapshot views seen in this section are provided OOTB and the content they contain is real-time, dynamic, and reflects the data gathered from the AppDynamics Browser Real User Monitoring Agent.
{{% /notice %}}

### Takeaways

- We've **identified the 5 web pages** related to the loan approval process **having issues**
- We have proved **the degraded end user response response times** for those pages **are backend related**
- We now have an **accurate mapping** of those **pages to the backend business transactions**
- We've **documented the drop-off rates** for each stage **of the loan approval process**

### [**Next**]({{< ref "55_flowmaps" >}}) <span style="color: #3e3071;"><i class='fas fa-cog fa-spin'></i></span>

<span class="small-text">In the next section **we'll use AppDynamics Flow Maps** to dive deeper and **gain valuable insights into the backend systems that service the frontend**.</span>

