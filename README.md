# Udagram

This template deploys a VPC, with a public and private subnets. It deploys an internet gateway, with a default route on the public subnets. It deploys a NAT gateway and default routes for them in the private subnet. It is also creating Bastion instance with which we can ssh into private subnet instances using aws ssm.

## Usage

1. Create a complete setup by running the below command.

    ```shell
    aws cloudformation create-stack --stack-name <stack_name> --parameters file://parameters.json --template-body file://vpc.yaml --capabilities CAPABILITY_IAM
    ```

2. Delete the stack by running the below command.

    ```shell
    aws cloudformation delete-stack --stack-name <stack_name>
    ```

### Components:

* [x] VPC
* [x] 2 Public Subnets
* [x] 1 private Subnet
* [x] NAT Gateway
* [x] Internet Gatway
* [x] Route table for public and private subnet with asssociation.
* [x] ALB LoadBalancer
* [x] Launch Configuration
* [x] Autoscaling Group
* [x] Listerner added to ALB
* [x] Target Group
* [x] Bastion Instance for SSH
* [x] SSM Agent for ssh to private instances from Bastion instance.