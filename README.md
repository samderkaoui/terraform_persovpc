# terraform_persovpc
Module VPC PERSO

```
module "vpc" {
  source = "github.com/Kaiser016X/terraform_persovpc"

  vpc_name             = "my-vpc"
  vpc_cidr             = "10.0.0.0/16"
  azs                  = ["eu-west-3a", "eu-west-3b"]
  private_subnet_cidrs = ["10.0.1.0/24", "10.0.2.0/24"]
  public_subnet_cidrs  = ["10.0.101.0/24", "10.0.102.0/24"]

  tags = {
    "Terraformed" = "True"
  }
}


#VPC Sam local
output "vpc_id" {
  value = module.vpc.vpc_id
}

output "public_subnets" {
  value = module.vpc.public_subnets
}

output "private_subnets" {
  value = module.vpc.private_subnets
}

output "nat_gateway_id" {
  value = module.vpc.nat_gateway_id
}

```
