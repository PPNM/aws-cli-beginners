## Create A Security Group
 ```
aws ec2 create-security-group - group-name my-sg - description "My security group" - region us-east-1 - vpc-id your-VPC-ID
 ```
 ## Create an Instance
 ```
aws ec2 run-instances --image-id ami-0198a868663199764 --instance-type t2.micro --region ap-southeast-1 --subnet-id your-Subnet-ID

aws ec2 describe-instance-status --output table|yaml|json
 ```
## Create an IGW

aws ec2 create-internet-gateway --tag-specifications ResourceType=internet-gateway,Tags=[{Key=Name,Value=my-igw}]
aws ec2 create-internet-gateway --tags Key="Name",Value="My-IGW"
aws ec2 describe-internet-gateways --output table
aws ec2 delete-subnet --subnet-id subnet-05dfd06b00635c11d
aws ec2 delete-vpc --vpc-id vpc-0084143f76d09739c

