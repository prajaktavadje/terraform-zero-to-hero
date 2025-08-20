provider "aws" {
    
    region = var.region_value
    access_key = var.access_key
    secret_key = var.secret_key 
  
}
resource "aws_instance" "normal" {
    ami = var.ami_value
    instance_type = var.instance_value
    tags ={
    Name = "my-new-terra"
    }
  
}
