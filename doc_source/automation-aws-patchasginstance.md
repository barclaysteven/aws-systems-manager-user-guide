# AWS-PatchAsgInstance

## Description

Systems Manager Automation - Patch instances in an Auto Scaling Group

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
- **Description**: (Required) ID of the Instance to patch. Only specify when not running from Maintenance Windows.

### LambdaRoleArn

- **Type**: String
- **Description**: (Optional) The ARN of the role that allows Lambda created by Automation to perform the actions on your behalf. If not specified a transient role will be created to execute the Lambda function.

### WaitForInstance

- **Type**: String
- **Default**: PT2M
- **Description**: (Optional) How long Automation should sleep for, to allow the instance come back into service

### WaitForReboot

- **Type**: String
- **Default**: PT5M
- **Description**: (Optional) How long Automation should sleep for, to allow a patched instance to reboot

## Examples

### Start the automation

```json
aws ssm start-automation-execution --document-name AWS-PatchAsgInstance --parameters 'TODO'
```

### Retrieve the execution output

```json
aws ssm get-automation-execution --automation-execution-id EXECUTIONID --output text --query 'AutomationExecution.Output'
```

## Required IAM Permissions

TODO

## Document Steps

1. **aws:createTags**
1. **aws:executeAutomation**
1. **aws:runCommand**
1. **aws:sleep**
1. **aws:executeAutomation**
1. **aws:createTags**
1. **aws:sleep**

## Outputs

None
