# AWS-RebootRdsInstance

## Description

Reboot RDS Instance

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

### InstanceId

- **Type**: String
- **Description**: (Required) Identifies the *RDS* instance subject to action.

## Examples

### Start the automation

```json
aws ssm start-automation-execution --document-name AWS-RebootRdsInstance --parameters 'TODO'
```

### Retrieve the execution output

```json
aws ssm get-automation-execution --automation-execution-id EXECUTIONID --output text --query 'AutomationExecution.Output'
```

## Required IAM Permissions

TODO

## Document Steps

1. **aws:assertAwsResourceProperty**
1. **aws:executeAwsApi**
1. **aws:waitForAwsResourceProperty**

## Outputs

None
