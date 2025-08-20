provider "aws" {
  region = "us-east-1"
  access_key = ""
  secret_key = "" 
}

# Security Group
resource "aws_security_group" "my_sg" {
  name        = "new-sg"
  description = "allow ssh"
  vpc_id      = ""

  ingress {
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}

# EC2 Instance
resource "aws_instance" "try" {
  ami                    = "ami-00ca32bbc84273381"
  instance_type          = "t2.micro"
  vpc_security_group_ids = [aws_security_group.my_sg.id]

  tags = {
    Name = "sg-ec2"
  }
}
