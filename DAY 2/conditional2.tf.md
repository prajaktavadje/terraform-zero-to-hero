# choose tag name
variable "is_test_instance" {
    description = "tag name"
    type = string
  
}

#porvider 
provider "aws" {

  region = "us-east-1"
  access_key = ""
  secret_key = ""
}
#resources
resource "aws_instance" "my-ec2" {
    ami = ""
    instance_type = "t2.micro"
    tags = {
      Name = var.is_test_instance ? "test_instance" : "prod_instance"
    }
  
}
