# AWS EKS Terraform Module

This repository contains a Terraform configuration for deploying an AWS EKS cluster using an existing VPC and subnet IDs.

## Repository structure

- `main.tf` - Root Terraform configuration for the EKS deployment
- `variables.tf` - Input variables for the root module
- `outputs.tf` - Root module outputs
- `terraform.tfvars` - Local variable values for this workspace
- `module/eks/` - EKS module implementation
- `.gitignore` - Ignores local Terraform state, Terraform cache, and sensitive files

## Prerequisites

- Terraform 1.0+ installed
- AWS CLI installed and configured
- An existing AWS profile with permissions to create EKS resources
- An existing VPC and subnet IDs to deploy EKS into

## Usage

1. Change to the repository root:

```bash
cd "/Users/abhi/Desktop/Data/Study Material/My-Workspace/aws-eks-module"
```

2. Ensure your AWS profile is available, for example:

```bash
export AWS_PROFILE=devops-admin
```

3. Initialize the working directory:

```bash
terraform init
```

4. Plan the deployment:

```bash
terraform plan
```

5. Apply the deployment:

```bash
terraform apply
```

## Variables

The configuration expects the following input variables:

- `vpc_id` - Existing VPC ID
- `subnet_ids` - List of existing subnet IDs for the EKS cluster
- `cluster_name` - Name of the EKS cluster
- `cluster_version` - Kubernetes version for EKS
- `node_groups` - EKS node group configuration

## Notes

- Do not commit `terraform.tfstate`, `terraform.tfstate.backup`, or `terraform.tfvars`.
- For long-term use, consider moving state to a remote backend such as S3.
