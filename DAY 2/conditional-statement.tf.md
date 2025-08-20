terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 6.0"
    }
  }
}

provider "aws" {
  region = "ap-south-1"
}

variable "environment" {
  default = "dev"
}

resource "aws_instance" "example" {
  ami           = ""
  instance_type = var.environment == "prod" ? "t3.medium" : "t2.micro"

  tags = {
    Name = "my-instance"
  }
}
