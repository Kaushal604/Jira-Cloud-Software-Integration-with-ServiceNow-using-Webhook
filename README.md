# Jira-Cloud-Software-Integration-with-ServiceNow-using-Webhook
**#################################### Rajesh Kaushal ##################################################################################**
Objective " Whenever a **Work Item of Type Epic is created in Jira** , an Event is triggered which will Automatically create a Service Now Ticket .
Once the Above is acheived All updates Done in Jira Will get reflected in ServiceNow Ticket .
Prerequisite:
Jira administrator Access
ServiceNow instance administrator Access
Follow below steps:

1.Create custom application/table in ServiceNow with below fields 
Table Name: Jira Staging Table | u_jira_stage
Fields:
Project Key | u_project_key
Project Name | u_project_name
Issue Key | u_issue_key
Issue Id | u_issue_id
Summary | u_summary
Description | u_description
2.Create Scripted REST API 
Create a scripted REST API resource to define the HTTP method, the processing script
Before you begin 
Role required: web_service_admin
Note: By default, any new Scripted REST API resource you create contains an ACL that prohibits users with the snc_external role from making requests to the API. 
Procedure
Navigate to System Web Services> Scripted REST APIs.
Select a scripted REST API record.
In the Resources related list, click New.
Enter a Name.
The resource name affects the URI for sending requests to the API.
Select the HTTP method this resource implements, In our case its POST
3: Refer the Javascript Shared in the Uploads **Name : RKDiraServiceNow** { Note you can fine tune it more as per requirenment using References passed as Request Params from Jira to SNOW }
4.Create a Jira User in ServiceNow
Username: Jira login email Id
Password: API Token  { Save the Details in a Seperate Notepad }
5. Fianlly we will Register a webhook in Jira wich will Invoke ServiceNOW
A.Go to Jira administration console > System> Webhooks (in the Advanced section).
B.You can also use the quick search (keyboard shortcut is .), then type 'webhooks'. 
C. Click Create a webhook.
In the form that is shown, enter the details for your new webhook. For more information on this, see Configuring a webhook later on this page.
To register your webhook, click Create. 
