# Viewing Canary Statistics and Details<a name="CloudWatch_Synthetics_Canaries_Details"></a>

You can view details about your canaries and see statistics about their runs\.

To be able to see all the details about your canary run results, you must be logged on to an account that has sufficient permissions\. For more information, see [Required Roles and Permissions for CloudWatch Canaries](CloudWatch_Synthetics_Canaries_Roles.md)\.

You can also view CloudWatch metrics created by your canaries\. These metrics are in the `CloudWatchSynthetics` namespace\. The metrics have the names `SuccessPercent`, `Failed`, and `Duration`\. These metrics have `CanaryName` as a dimension\. Canaries that check a GUI workflow also have `StepName` as a dimension\.

For more information about viewing CloudWatch metrics, see [Viewing Available Metrics](viewing_metrics_with_cloudwatch.md),

**To view canary statistics and details**

1. Open the CloudWatch console at [https://console\.aws\.amazon\.com/cloudwatch/](https://console.aws.amazon.com/cloudwatch/)\.

1. In the navigation pane, choose **Canaries**\.

   In the details about the canaries that you have created:
   + **Status** visually shows how many of your canaries have passed their most recent runs\.
   + In the graph under **Canary runs**, each point represents one minute of your canaries’ runs\. You can pause on a point to see details\.
   + Near the bottom of the page is a table displaying all canaries\. The column on the right shows the alarms created for each canary\. Only alarms that conform to the naming standard for canary alarms are displayed\. This standard is `Synthetics-Alarm-canaryName-index `\. Canary alarms that you create in the **Synthetics** section of the CloudWatch console automatically use this naming convention\. If you create canary alarms in the **Alarms** section of the CloudWatch console or by using AWS CloudFormation, and you don't use this naming convention, the alarms work but they do not appear in this list\.

1. To see more details about a single canary, choose a point in the **Status** graph or choose the name of the canary in the **Canaries** table\.

   In the details about that canary:
   + Under **Canary runs**, you can choose one of the lines to see details about that run\.
   + Under the graph, you can choose **Screenshot**, **HAR file**, or **Logs** to see these types of details\.

     The logs for canary runs are stored in S3 buckets and in CloudWatch Logs\.

     Screenshots show how your customers view your webpages\. You can use the HAR files \(HTTP Archive files\) to view detailed performance data about the webpages\. You can analyze the list of web requests and catch performance issues such as time to load for an item\. Log files show the record of interactions between the canary run and the webpage and can be used to identify details of errors\.

     If the canary uses the `syn-nodejs-2.0-beta` runtime or later, you can sort the HAR files by status code, request size, or duation\.

1. If the canary uses the `syn-nodejs-2.0-beta` runtime or later and the canary executes steps in its script, you can choose a **Steps** tab\. This tab displays a list of the canary's steps, each step's status, failure reason, URL after step execution, screenshots, and duration of step execution\.