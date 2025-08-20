# to setup ec2-instances in mutiple region

# Singapore Provider
provider "aws" {
  alias  = "ap-southeast-1"
  region = "ap-southeast-1"
  access_key = ""
  secret_key =""
}

# Sydney Provider
provider "aws" {
  alias  = "ap-southeast-2"
  region = "ap-southeast-2"
  access_key = ""
  secret_key = ""

}

# Singapore EC2
resource "aws_instance" "example1" {
  ami           = "" # Singapore AMI
  instance_type = "t2.micro"
  provider      = aws.ap-southeast-1

  tags = {
    Name = "Singapore-Instance"
  }
}

# Sydney EC2
resource "aws_instance" "example2" {
  ami           = "" # Sydney AMI
  instance_type = "t2.micro"
  provider      = aws.ap-southeast-2

  tags = {
    Name = "Sydney-Instance"
  }
}
