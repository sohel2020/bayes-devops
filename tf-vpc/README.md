## VPC Creattion with terraform

## Prerequisites:

1. AWS CLI
2. Terraform >= 0.12

## Design Choice
In the VPC creating steps I'm creating 6 subnet. 3 subnet will be directly attached with IGW (aka: public subnet) and 3 subnet will be connected VIA NAT-GW.

## Installation Steps
```bash
$ terraform init
$ terraform plan
$ terraform apply -auto-approve
```
