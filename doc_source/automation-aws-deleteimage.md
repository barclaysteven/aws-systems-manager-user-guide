# AWS-DeleteImage

## Description

Delete Amazon Machine Image (AMI) and all associated snapshots.

## Document Type

Automation

## Owner

Amazon

## Platform(s)

Windows,Linux

## Parameters

### AutomationAssumeRole

- **Type**: String
- **Description**: (Optional) The ARN of the role that allows Automation to perform the actions on your behalf.

### ImageId

- **Type**: String
- **Description**: (Required) The ID of the Amazon Machine Image (AMI).

## Examples

### Start the automation

```json
aws ssm start-automation-execution --document-name AWS-DeleteImage --parameters 'TODO'
```

### Retrieve the execution output

```json
aws ssm get-automation-execution --automation-execution-id EXECUTIONID --output text --query 'AutomationExecution.Output'
```

## Required IAM Permissions

TODO

## Document Steps

1. **aws:deleteImage**

## Outputs

None
