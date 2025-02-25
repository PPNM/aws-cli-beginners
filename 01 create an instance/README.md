## Create A Security Group
 ```
aws ec2 create-security-group - group-name my-sg - description "My security group" - region us-east-1 - vpc-id your-VPC-ID
 ```
 ## Create an Instance
 ```
aws ec2 run-instances --image-id ami-0198a868663199764 --instance-type t2.micro --region ap-southeast-1 --subnet-id your-Subnet-ID
 ```
