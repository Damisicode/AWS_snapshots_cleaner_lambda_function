# AWS Snapshots Cleaner Lambda Function

Are you tired of paying for unused EBS snapshots on AWS? Do you often forget to delete snapshots attached to EBS volumes, leading to unnecessary costs? If so, the "AWS Snapshots Cleaner Lambda Function" might be just what you need!

This Lambda function is designed to automatically delete EBS snapshots when they meet specific criteria. In this case, it targets snapshots associated with an EBS volume that has been created within the last six months and is no longer attached to an EC2 instance. By using this function, you can effectively manage your snapshots and reduce your AWS costs.

## Why Use This Solution?

The problem of forgotten snapshots can result in significant costs on your AWS bill. There are a few ways to address this issue:

1. **Manual Deletion**: You can periodically check for and delete snapshots manually, but this can be time-consuming and prone to human error.

2. **Moving to Glacier**: Another option is to move snapshots to Amazon Glacier, a more cost-effective storage class. This allows you to retain snapshots for future use while reducing immediate costs.

3. **Automated Deletion**: This Lambda function automates the process by deleting snapshots that meet specific criteria, reducing the chances of forgetting to clean up unused snapshots.

## Features

- **Automated Cleanup**: The Lambda function will automatically delete snapshots that are no longer needed, helping you avoid unnecessary costs.
- **Customizable Timeframe**: You can configure the Lambda function to consider snapshots created within a specific timeframe (e.g., the last six months).
- **Integration with Amazon EventBridge**: Improve automation by attaching rules in Amazon EventBridge to run the Lambda function at specific time intervals.
- **Slack Integration**: You can integrate this solution with a Slack channel to confirm the snapshots are not needed before deletion, adding an extra layer of security.

## Usage

1. **Create Lambda Function**: Deploy the Lambda function in your AWS account. You can use the provided code as a starting point.

2. **Configure EventBridge Rules**: Attach rules in Amazon EventBridge to trigger the Lambda function at the desired schedule. For example, you can run it daily or weekly.

3. **Optional Slack Integration**: Integrate the Lambda function with a Slack channel to receive notifications and confirm snapshot deletions.

4. **Customize Timeframe**: Modify the Lambda function to specify the desired timeframe for snapshot deletion.

## How It Works

1. The Lambda function runs based on the configured schedule via EventBridge rules.

2. It scans your AWS account for snapshots attached to EBS volumes.

3. For each snapshot, it checks if it meets the specified criteria (e.g., created within the last six months and no longer attached to an EC2 instance).

4. If a snapshot matches the criteria, it is deleted.

## Contribution

Contributions and improvements to this Lambda function are welcome. If you have suggestions, feature requests, or bug fixes, please feel free to submit a pull request or open an issue.

By using the "AWS Snapshots Cleaner Lambda Function," you can effectively manage your EBS snapshots and reduce unnecessary costs while automating the cleanup process. Enjoy a cleaner, more cost-effective AWS experience!
