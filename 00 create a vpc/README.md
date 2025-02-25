## Enable Auto Prompt
 ```
 aws --cli-auto-prompt
```
 ## create a vpc with CIDR
 ```
 aws ec2 create-vpc --cidr-block 10.30.5.0/24 --query Vpc.VpcId --output text
 aws ec2 describe-vpcs --output table
```
 ## Create tags
 ```
 aws ec2 create-tags --resources vpc-0084143f76d09739c --tags Key="Name",Value="MyVpc"
 aws ec2 describe-vpcs --filters Name=tag:Name,Values=MyVpc --output table
```
 ## Create Subnet
 ```
 aws ec2 create-subnet --vpc-id vpc-0084143f76d09739c --cidr-block 10.30.5.0/25 --query Subnet.SubnetId --output text
 aws ec2 describe-subnets --filters Name=vpc-id,Values=vpc-0084143f76d09739c --output table
```
