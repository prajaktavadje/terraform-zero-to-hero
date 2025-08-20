variable "instance_type" {
  description = "Instance type for EC2"
  type        = string
  default     = "t2.micro"
}

 provider "aws" {
  region     = ""
  access_key = ""
 secret_key = ""
}

resource "aws_instance" "my-ec2" {
  ami           = ""
  instance_type = var.instance_type

  tags = {
    Name = "my-terra"
  }
}
