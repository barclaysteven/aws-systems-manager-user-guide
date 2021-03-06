# AWS-StopEC2InstanceWithApproval

## Description

Stop EC2 instances(s) with approval

## Document Type

Automation

## Owner

Amazon

## Platform(s)

Windows,Linux

## Parameters

### Approvers

- **Type**: StringList
- **Description**: (Required) IAM user or user arn of approvers for the automation action

### AutomationAssumeRole

- **Type**: String
- **Description**: (Optional) The ARN of the role that allows Automation to perform the actions on your behalf.

### InstanceId

- **Type**: StringList
- **Description**: (Required) EC2 Instance(s) to stop

### SNSTopicArn

- **Type**: String
- **Description**: (Required) The SNS topic ARN used to send pending approval notification for stop instance action. The SNS topic name must start with Automation.

## Examples

### Start the automation

```json
aws ssm start-automation-execution --document-name AWS-StopEC2InstanceWithApproval --parameters 'TODO'
```

### Retrieve the execution output

```json
aws ssm get-automation-execution --automation-execution-id EXECUTIONID --output text --query 'AutomationExecution.Output'
```

## Required IAM Permissions

TODO

## Document Steps

1. **aws:approve**
1. **aws:changeInstanceState**

## Outputs

None
