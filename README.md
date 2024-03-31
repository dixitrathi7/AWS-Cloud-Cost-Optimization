# AWS-Cloud-Cost-Optimization
The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.
# Project Overview:
Objective:-  AWS Cloud Cost Optimization by identifying and deleting stale EBS snapshots that are no longer associated with any active EC2 instance.

Components:-  Utilizes AWS Lambda function to automate the identification and deletion process.

# Resources Used in the Project:
1. AWS Lambda:-  A serverless compute service that runs code in response to triggers and automatically manages the compute resources required by that code. Lambda is used to execute the function that identifies and deletes stale EBS snapshots.
2. AWS Identity and Access Management (IAM):-   AM roles are utilized to grant necessary permissions to the Lambda function, allowing it to interact with EC2 and EBS resources.
3. Amazon EC2:- The function retrieves a list of active EC2 instances (running and stopped) to check for associations with EBS snapshots.
4. Amazon EBS (Elastic Block Store):- EBS snapshots are the target resources for identification and potential deletion.

# Implementation Steps:
1.Fetch EBS Snapshots: The Lambda function fetches all EBS snapshots owned by the AWS account.

2.Retrieve Active EC2 Instances: It retrieves a list of active EC2 instances, including both running and stopped instances.

3.Check Snapshot Associations: For each snapshot, the function checks if the associated volume is not associated with any active instance. If it finds a stale snapshot (one that is not associated with any active instance), it proceeds to the deletion step.

4.Delete Stale Snapshots: Upon identifying stale snapshots, the Lambda function deletes them to optimize storage costs.

# Workflow Summary:
1.Trigger: The Lambda function can be triggered periodically using a scheduled event (e.g., CloudWatch Events) to ensure regular identification and deletion of stale snapshots.

2. Execution: Upon trigger, the Lambda function executes its logic to identify stale EBS snapshots and delete them accordingly.

3. Logging and Monitoring: Logging and monitoring mechanisms (e.g., CloudWatch Logs, CloudWatch Metrics) can be implemented to track the execution of the Lambda function and any potential errors encountered during the process.
