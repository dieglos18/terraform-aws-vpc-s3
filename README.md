# Terraform AWS VPC and S3 Bucket

This project creates AWS infrastructure using Terraform as part of Free Tier practice exercises.

## 📋 Overview

This Terraform configuration creates:
- A custom VPC with CIDR block 10.0.0.0/16
- A public subnet with CIDR block 10.0.1.0/24
- An Internet Gateway
- A route table with internet access
- An S3 bucket with versioning and public access blocked

## 🚀 Prerequisites

Before you begin, ensure you have the following installed:
- [Terraform](https://www.terraform.io/downloads.html) (>= 1.0)
- [AWS CLI](https://aws.amazon.com/cli/) configured with credentials
- An AWS account with appropriate permissions

## 🛠️ Installation

1. Clone this repository:
```bash
git clone https://github.com/YOUR_USERNAME/terraform-aws-vpc-s3.git
cd terraform-aws-vpc-s3
```

2. Configure your AWS credentials:
```bash
aws configure
```

3. Initialize Terraform:
```bash
terraform init
```

## 📖 Usage

### View the execution plan
```bash
terraform plan
```

### Apply the configuration
```bash
terraform apply
```
Type `yes` when prompted to confirm.

### View outputs
```bash
terraform output
```

### Destroy the infrastructure
```bash
terraform destroy
```
Type `yes` when prompted to confirm.

## 📁 Project Structure
```
.
├── main.tf           # Main Terraform configuration
├── variables.tf      # Variable definitions
├── outputs.tf        # Output definitions
├── .gitignore        # Git ignore rules
└── README.md         # This file
```

## 🔧 Configuration

You can customize the following variables by creating a `terraform.tfvars` file:
```hcl
aws_region          = "us-east-1"
project_name        = "my-project"
environment         = "dev"
vpc_cidr            = "10.0.0.0/16"
public_subnet_cidr  = "10.0.1.0/24"
```

## 📊 Resources Created

| Resource Type | Name | Description |
|--------------|------|-------------|
| VPC | main | Virtual Private Cloud |
| Subnet | public | Public subnet in AZ a |
| Internet Gateway | main | Internet connectivity |
| Route Table | public | Routes for public subnet |
| S3 Bucket | main | Object storage bucket |

## 💰 Cost Considerations

All resources are designed to stay within AWS Free Tier limits:
- VPC, Subnets, Internet Gateway: **Free**
- S3: **5GB free** for 12 months
- **Important**: Always run `terraform destroy` when done practicing!

## ⚠️ Important Notes

1. **Never commit** `terraform.tfvars` or `.tfstate` files (they're in `.gitignore`)
2. **Always destroy** resources after practice to avoid charges
3. The S3 bucket name must be globally unique
4. Ensure your AWS credentials have sufficient permissions

## 🤝 Contributing

Feel free to fork this project and submit pull requests with improvements!

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 👤 Author

Your Name - [@your_github](https://github.com/YOUR_USERNAME)

## 🙏 Acknowledgments

- AWS Free Tier documentation
- Terraform documentation
- HashiCorp Learn tutorials