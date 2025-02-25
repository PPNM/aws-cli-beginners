## Enable Auto Prompt
 ```
 aws --cli-auto-prompt
```
 ## create a vpc with CIDR
 ```
 aws ec2 create-vpc --cidr-block x.x.x.x/x --query Vpc.VpcId --output text
 aws ec2 describe-vpcs --output table
```
 ## Create tags
 ```
 aws ec2 create-tags --resources your-VPC-ID --tags Key="Name",Value="MyVpc"
 aws ec2 describe-vpcs --filters Name=tag:Name,Values=MyVpc --output table
```
 ## Create Subnet
 ```
 aws ec2 create-subnet --vpc-id your-VPC-ID --cidr-block x.x.x.x/x --query Subnet.SubnetId --output text
 aws ec2 describe-subnets --filters Name=vpc-id,Values=your-VPC-ID --output table
```
