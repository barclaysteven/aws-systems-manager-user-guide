# AWS-UpdateLinuxAmi

## Description

Updates AMI with Linux distribution packages and Amazon software. For details,see https://docs.aws.amazon.com/systems-manager/latest/userguide/automation-awsdocs-linux.html

## Document Type

Automation

## Owner

Amazon

## Platform(s)

Windows,Linux

## Parameters

### AutomationAssumeRole

- **Type**: String
- **Default**: arn:aws:iam::{{global:ACCOUNT_ID}}:role/AutomationServiceRole
- **Description**: (Required) The ARN of the role that allows Automation to perform the actions on your behalf.

### ExcludePackages

- **Type**: String
- **Default**: none
- **Description**: (Optional) Names of packages to hold back from updates, under all conditions. By default ("none"), no package is excluded.

### IamInstanceProfileName

- **Type**: String
- **Default**: ManagedInstanceProfile
- **Description**: (Required) The instance profile that enables Systems Manager (SSM) to manage the instance.

### IncludePackages

- **Type**: String
- **Default**: all
- **Description**: (Optional) Only update these named packages. By default ("all"), all available updates are applied.

### InstanceType

- **Type**: String
- **Default**: t2.micro
- **Description**: (Optional) Type of instance to launch as the workspace host. Instance types vary by region. Default is t2.micro.

### PostUpdateScript

- **Type**: String
- **Default**: none
- **Description**: (Optional) URL of a script to run after package updates are applied. Default ("none") is to not run a script.

### PreUpdateScript

- **Type**: String
- **Default**: none
- **Description**: (Optional) URL of a script to run before updates are applied. Default ("none") is to not run a script.

### SourceAmiId

- **Type**: String
- **Description**: (Required) The source Amazon Machine Image ID.

### TargetAmiName

- **Type**: String
- **Default**: UpdateLinuxAmi_from_{{SourceAmiId}}_on_{{global:DATE_TIME}}
- **Description**: (Optional) The name of the new AMI that will be created. Default is a system-generated string including the source AMI id, and the creation time and date.

## Examples

### Start the automation

```json
aws ssm start-automation-execution --document-name AWS-UpdateLinuxAmi --parameters 'TODO'
```

### Retrieve the execution output

```json
aws ssm get-automation-execution --automation-execution-id EXECUTIONID --output text --query 'AutomationExecution.Output'
```

## Required IAM Permissions

TODO

## Document Steps

1. **aws:runInstances**
1. **aws:runCommand**
1. **aws:runCommand**
1. **aws:changeInstanceState**
1. **aws:createImage**
1. **aws:changeInstanceState**

## Outputs

createImage.ImageId
