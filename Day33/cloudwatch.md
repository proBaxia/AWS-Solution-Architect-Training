# AWS CloudWatch Logging

## Step-1: Pre-requisites
- You must have activated aws.amazon.com account.
- You have the sample tomcat application.Download it to the tomcat windows machine.
  Download -  https://github.com/cloudnloud/AWS-Solution-Architect-Training/blob/129231177f6f3c9b0f4590306ffd7aaffd3e9b3a/Day33/gameoflife.war

 
## Step-2: CloudWatch
 - **What is CloudWatch:** Amazon CloudWatch is a monitoring and management service that provides data and actionable insights for AWS, hybrid, and on-premises applications and infrastructure resources. With CloudWatch, you can collect and access all your performance and operational data in form of logs and metrics from a single platform. 

## Step-2: CloudWatch Implementation Steps
 - ** Please find an overview of the steps to install\configure the CloudWatch Agent on Windows Instance per your request as below:**
     1.	Attach the required IAM permission policy to the EC2 instance profile [1].
     2.	Download\install CloudWatch Unified Agent on EC2 instance [2]
     3.	Configure CloudWatch Agent to publish Metrics\Logs to CloudWatch Console [3] and [4].
     4.	Run CloudWatch Agent [5].


## Step-2.1: Attach IAM policy to EC2 Machine

	1.	Sign in to the AWS Management Console and open the IAM console at https://console.aws.amazon.com/iam 
	
	2. Create IAM Role.
         In Select type of trusted entity --> AWS Service --> Common UseCase --> Choose EC2 --> Click Next: Permissions --> search CloudWatchAgentServerPolicy and attach it --> save this role as CloudWatchAgentServerRole
  

     
     3.	In the navigation pane on the left, choose Roles
     4.	Choose the role that is attached as an Instance Profile to your EC2 Instance in question.
     5.	Click on “Attach policies” button.
     6.	In the list of policies, search for a policy with the name of “CloudWatchAgentServerPolicy”.
     7.	Select the check box next to CloudWatchAgentServerPolicy. 
     8.	Click on “Attach Policy” button.


## Step-3: Install Cloudwatch Agent Software



## Step-4: Install Cloudwatch Agent Software

     - Download the Agent :
       https://s3.amazonaws.com/amazoncloudwatch-agent/windows/amd64/latest/amazon-cloudwatch-agent.msi 
     - 	Install the Agent
     - 	Check if it is installed (Status should be Stopped)
     -  Run PowerShell as Administrator
```
cd “C:\Program Files\Amazon\AmazonCloudWatchAgent\”
.\amazon-cloudwatch-agent-ctl.ps1 -a status
```

## Step-5: Configure CloudWatch Agent

     - Configure CloudWatch Agent to publish Metrics\Logs to CloudWatch Console), please run the below follow the below instructions:
     - You can create the CloudWatch Agent Configuration File either automatically [3] or manually [4].


```
cd “C:\Program Files\Amazon\AmazonCloudWatchAgent\”

amazon-cloudwatch-agent-config-wizard C:\Program Files\Amazon\AmazonCloudWatchAgent\ folder
```

- answer one by one and finally config.json file will be created.
- Make sure config.json file is placed into 


## Step-6: Push the updated Config to Cloudwatch Agent


     - Run CloudWatch Agent), please run the below command in order:
     - Run PowerShell as Administrator
```
cd “C:\Program Files\Amazon\AmazonCloudWatchAgent\”
```

     -	Run the Agent with fetch-config to instruct the agent to take the new configuration form the JSON file.
```
.\amazon-cloudwatch-agent-ctl.ps1 -a fetch-config -m ec2 -c file:config.json -s
```




## Step-7: Check the log Groups in AWS.AMAZON.Com - Cloudwatch

-  Explore cloudwatch ewly created log groups and logs etc.