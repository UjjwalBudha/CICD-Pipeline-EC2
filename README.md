# Terraform AWS EC2 Instance Setup

This Terraform project automates the setup of an EC2 instance on AWS. It provisions the necessary resources like VPC, subnet, security group, and EC2 instance itself, and installs a website using a provided script.

## Requirements

- Terraform installed on your local machine.
- AWS account with appropriate permissions.
- Access key and secret key for the AWS account.

## Usage

1. Clone this repository to your local machine.

git clone <repository_url>

css
Copy code

2. Navigate to the project directory.

cd <project_directory>

markdown
Copy code

3. Initialize Terraform.

terraform init

vbnet
Copy code

4. Review and modify the `terraform.tfvars` file to set your AWS access key, secret key, and any other variables.

5. Optionally, customize the `install_techmax.sh` script to install your desired website or application on the EC2 instance.

6. Apply the Terraform configuration to create the infrastructure.

terraform apply

vbnet
Copy code

7. After the setup is complete, the URL of the server will be printed to the console.

## Configuration Details

### `main.tf`

This file defines the main Terraform configuration. It provisions the EC2 instance, configures the AWS provider, sets up the Terraform backend to store state in an S3 bucket, creates a default VPC if one does not exist, creates a default subnet, and configures a security group for the EC2 instance.

### `output.tf`

This file defines the output configuration. It prints the URL of the EC2 instance to the console after provisioning.

### `variables.tf`

This file defines the input variables used in the Terraform configuration. It includes variables for AWS access key, secret key, and other configurable parameters.

### `terraform.tfvars`

This file contains the values for the input variables defined in `variables.tf`. You should populate this file with your AWS access key, secret key, and any other required variables.

### `install_techmax.sh`

This shell script is executed on the EC2 instance to install the desired website or application. You can customize this script according to your requirements.

## Cleanup

To avoid incurring unnecessary costs, it's essential to destroy the infrastructure when it's no longer needed. You can do this by running:

terraform destroy
