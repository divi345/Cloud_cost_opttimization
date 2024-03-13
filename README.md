The project aimed to optimize cloud costs on AWS by efficiently managing EBS snapshots using AWS CloudWatch and Lambda functions. Here's how the project works:

Lambda Function Setup: A Lambda function is created using Python. This function will be responsible for identifying and managing unused EBS snapshots.

Integration with CloudWatch Events: The Lambda function is configured to be triggered by CloudWatch events. CloudWatch is used to schedule the execution of the Lambda function at regular intervals, allowing for automated snapshot management.

Snapshot Monitoring: Within the Lambda function, the boto3 library is utilized to interact with AWS services. Specifically, the function scans through the list of EBS snapshots associated with the account.

Identifying Unused Snapshots: The Lambda function identifies snapshots that are no longer associated with any running instances or volumes. These are considered as potentially unused snapshots that could be deleted to optimize costs.

Action: Depending on the project requirements, the Lambda function can take one of two actions:

Delete Unused Snapshots: Unused snapshots are deleted to free up storage resources and reduce costs.
Notify Snapshot Owners: Alternatively, if it's necessary to retain unused snapshots for backup or other purposes, notifications are sent out to the respective snapshot owners, informing them about the unused snapshots.
