## Create A Security Group
 ```
aws ec2 create-security-group --group-name my-sg --description 'My security group' --region your-region --vpc-id your-VPC-ID

 ```
--group-name: Name of the security group.

--description: Description of the security group.

--region: The AWS region where the security group will be created.

--vpc-id: The ID of the VPC where the security group will be created.

 ## Create an Instance
 ```
aws ec2 run-instances --image-id ami-0198a868663199764 --instance-type t2.micro --region your-region --subnet-id your-Subnet-ID
 --security-group-ids sg-xxxxxxxx

aws ec2 describe-instance-status --output table|yaml|json
 ```
--image-id: The AMI ID for the instance.

--instance-type: The instance type (e.g., t2.micro).

--subnet-id: The subnet where the instance will be launched.

--security-group-ids: The security group ID(s) to associate with the instance.

## Create an IGW

 ```
aws ec2 create-internet-gateway --tag-specifications 'ResourceType=internet-gateway,Tags=[{Key=Name,Value=my-igw}]'
 ```
--tag-specifications: Adds tags to the internet gateway.
 ```
aws ec2 describe-internet-gateways --output table
 ```
The --output table flag formats the output in a readable table format. You can also use json or yaml

## Attach IGW to VPC
 ```
 aws ec2 attach-internet-gateway --internet-gateway-id your-igw-id --vpc-id your-vpc-id
  ```
## Verify the Attachment
 ```
 aws ec2 describe-internet-gateways --internet-gateway-ids your-igw-id --output table
 ```
## Detaching an IGW
 ```
 aws ec2 detach-internet-gateway --internet-gateway-id your-igw-id --vpc-id your-vpc-id
 ```

 ## Deleting an Internet Gateway
  
 ```
aws ec2 delete-subnet --subnet-id your-sunbnet-id
 ```
 ## Deleting VPC
 ```
aws ec2 delete-vpc --vpc-id your-vpc-id
```
//Important Notes:
Dependencies:

Before deleting a VPC, ensure all dependent resources (e.g., subnets, instances, internet gateways) are deleted or detached.

For example:

Terminate all instances in the VPC.

Delete all subnets.

Detach and delete the internet gateway.

Order of Operations:

Delete resources in the following order to avoid errors:

Terminate instances.

Delete subnets.

Detach and delete internet gateways.

Delete the VPC.

Region:

Ensure you are working in the correct AWS region. Use the --region flag if necessary.

Tagging:

Use tags (e.g., Name=my-igw) to easily identify and manage resources.





