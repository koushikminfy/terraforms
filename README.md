##  Setup


###  Configuration

Edit `terraform.tfvars`:
hcl
aws_region     = "us-west-2"
project_name   = "my-terraform-project"
key_name       = "your-key-pair-name"  # Replace with your actual key pair
instance_type  = "t3.micro"
ebs_volume_size = 10


##  Deploy

bash
terraform init
terraform validate
terraform plan
terraform apply  # type 'yes' when prompted


##  Access & Verify

* Get Load Balancer URL:

 bash
  terraform output load_balancer_url
  

* SSH to EC2:

  bash
  ssh -i your-key.pem ec2-user@<instance-ip>
  

* Check EBS mount:

  bash
  df -h


##  Cleanup

bash
terraform destroy


##  Notes

* Ensure security group rules allow HTTP/SSH as needed.
* Use the AWS console to verify ALB and EC2 health checks.
* Monitor EBS mounts and storage size as per configuration.
