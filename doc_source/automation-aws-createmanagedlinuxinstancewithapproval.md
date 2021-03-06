# AWS-CreateManagedLinuxInstanceWithApproval

## Description

Creates a Linux Managed Instance with approval

## Document Type

Automation

## Owner

Amazon

## Platform(s)

Windows,Linux

## Parameters

### AmiId

- **Type**: String
- **Description**: (Required) AMI id to use for launching the instance.

### Approvers

- **Type**: StringList
- **Description**: (Required) IAM user or user arn of approvers for the automation action

### AutomationAssumeRole

- **Type**: String
- **Description**: (Optional) The ARN of the role that allows Automation to perform the actions on your behalf

### GroupName

- **Type**: String
- **Default**: SSMSecurityGroupForLinuxInstances
- **Description**: (Required) Security Group Name to create.

### InstanceType

- **Type**: String
- **Default**: t2.medium
- **Description**: (Required) Type of instance to launch. Default is t2.medium.

### KeyPairName

- **Type**: String
- **Description**: (Required) Key pair to use when creating instance.

### RemoteAccessCidr

- **Type**: String
- **Default**: 0.0.0.0/0
- **Description**: (Required) Creates Security group with port for SSH(Port range 22) open to IPs specified by CIDR (default is 0.0.0.0/0). If the security group already exists it will not be modified and rules will not be changed.

### RoleName

- **Type**: String
- **Default**: SSMManagedInstanceProfileRole
- **Description**: (Required) Role Name to create.

### SNSTopicArn

- **Type**: String
- **Description**: (Required) The SNS topic ARN used to send pending approval notification for creating a new managed instance. The SNS topic name must start with Automation.

### StackName

- **Type**: String
- **Default**: CreateManagedInstanceStack{{automation:EXECUTION_ID}}
- **Description**: (Optional) Specify stack name used by this document

### SubnetId

- **Type**: String
- **Default**: Default
- **Description**: (Required) New instance will be deployed into this subnet or in the default subnet if not specified.

### VpcId

- **Type**: String
- **Default**: Default
- **Description**: (Required) New instance will be deployed into this vpc or in the default vpc if not specified.

## Examples

### Start the automation

```json
aws ssm start-automation-execution --document-name AWS-CreateManagedLinuxInstanceWithApproval --parameters 'TODO'
```

### Retrieve the execution output

```json
aws ssm get-automation-execution --automation-execution-id EXECUTIONID --output text --query 'AutomationExecution.Output'
```

## Required IAM Permissions

TODO

## Document Steps

1. **aws:approve**
1. **aws:createStack**
1. **aws:deleteStack**

## Outputs

None
