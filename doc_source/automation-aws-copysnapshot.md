# AWS-CopySnapshot

## Description

Copy Snapshot

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

### Description

- **Type**: String
- **Description**: (Optional) A description for the EBS snapshot.

### LambdaAssumeRole

- **Type**: String
- **Description**: (Optional) The ARN of the role assumed by lambda

### SnapshotId

- **Type**: String
- **Description**: (Required) The ID of the EBS snapshot to copy.

### SourceRegion

- **Type**: String
- **Description**: (Required) The region where the source snapshot currently exists.

## Examples

### Start the automation

```json
aws ssm start-automation-execution --document-name AWS-CopySnapshot --parameters 'TODO'
```

### Retrieve the execution output

```json
aws ssm get-automation-execution --automation-execution-id EXECUTIONID --output text --query 'AutomationExecution.Output'
```

## Required IAM Permissions

TODO

## Document Steps

1. **aws:createStack**
1. **aws:invokeLambdaFunction**
1. **aws:deleteStack**

## Outputs

copySnapshot.Payload
