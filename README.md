# aws-cloudformation-connector
THIS SCRIPT IS PROVIDED TO YOU "AS IS."  TO THE EXTENT PERMITTED BY LAW, QUALYS HEREBY DISCLAIMS ALL WARRANTIES AND LIABILITY FOR THE PROVISION OR USE OF THIS SCRIPT.  IN NO EVENT SHALL THESE SCRIPTS BE DEEMED TO BE CLOUD SERVICES AS PROVIDED BY QUALYS

CloudFormation Template to create a Qualys EC2 Connector and associated role and
managed policy. To run the script you will need to supply credentials for the
Qualys user name and password for Qualys API Access.

Parameters:
  UserName:
    Default: {supply_Qualys_user_name}
...

  Password:
    Default: {supply_Qualys_user_password}

This CloudFormation template only activates a EC2 connector with the VM module.
If the PC module is needed, the activated modules section of the Python code
will need to be modified.

If you want to change the Role or Policy name you can edit these settings in line number 27 and/or 182

RoleName:
  Default: CF-QualysEC2ConnectorRole

...

QualysEC2RoleCrossAccount:
  Type: AWS::IAM::ManagedPolicy
  Properties:
    ManagedPolicyName: "QualysEC2RoleCrossAccount"
