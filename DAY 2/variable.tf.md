variable "ami_value" {
    description = "value of ami_id"
    type = string
    default = ""
  
}
variable "instance_value" {
  description = "instance type"
  type = string
  default = "t2.micro"
}
variable "region_value" {
    description = "to specifiy region"
    type = string
    default = ""

}
variable "access_key" {
    type = string  
}
variable "secret_key" {  
  type = string
}
