# _Terraform Module: terraform-module-aws-vpc-subnet_
_Terraform module for **_AWS VPC Subnet_**_


<!--BEGIN STABILITY BANNER-->
---

![_Code : Stable_](https://img.shields.io/badge/Code-Stable-brightgreen?style=for-the-badge&logo=github)

> **_This is a stable example. It should successfully build out of the box_**
>
> _This examples does is built on Construct Libraries marked "Stable" and does not have any infrastructure prerequisites to build._

---
<!--END STABILITY BANNER-->

## _General_

_This module can be used to deploy a_ **_VPC Subnet_** _on AWS Cloud Provider......_


---

## _Prerequisites_

_This module needs **_Terraform 0.12.23_** or newer._
_You can download the latest Terraform version from_ [_here_](https://www.terraform.io/downloads.html).



---

## _Features Branches_

_Below we are able to check the resources that are being created as part of this module call:_

- **_VPC Subnet_**


---

## _Usage_

## _Using this repo_

_To use this module, add the following call to your code:_

- **_Sample Code:_**

```tf
module "vpc_subnet" {
  source = "git::https://github.com/nitinda/terraform-module-aws-vpc-subnet.git?ref=master"


  vpc_id     = var.vpc_id
  cidr_block = "172.2.0.0/24"
  tags       = {
    Environment = "prod"
    Project     = "POC"
  }

}
```

```tf
module "vpc_subnet" {
  source = "git::https://github.com/nitinda/terraform-module-aws-vpc-subnet.git?ref=master"


  vpc_id     = var.vpc_id
  availability_zone = "eu-central-1c"
  cidr_block = "172.2.0.0/24"
  tags       = {
    Environment = "prod"
    Project     = "POC"
  }

}
```

```tf
module "public_1a" {
  source = "git::https://github.com/nitinda/terraform-module-aws-vpc-subnet.git?ref=master"

  vpc_id            = module.vpc.id
  cidr_block        = "10.1.0.0/16"
  availability_zone = "eu-central-1a"
  tags       = merge(
    var.common_tags,
    {
      Environment = "prod"
      Name        = "vpc-subnet-public-1a"
    }
  )
}
```

```tf
module "public_1a" {
  source = "git::https://github.com/nitinda/terraform-module-aws-vpc-subnet.git?ref=master"

  vpc_id               = module.vpc.id
  cidr_block           = "10.1.0.0/16"
  availability_zone_id = "euc1-az2"
  tags       = merge(
    var.common_tags,
    {
      Environment = "prod"
      Name        = "vpc-subnet-public-1a"
    }
  )
}
```

---

## _Inputs_

_The variables required in order for the module to be successfully called from the deployment repository are the following:_

|**_Variable_** | **_Description_** | **_Type_** | **_Argument Status_** |
|:----|:----|-----:|:---:|
| **_availability\_zone_** | _The AZ for the subnet_ | _string_ | **_Optional <br/> (Default - null)_** |
| **_availability\_zone\_id_** | _The AZ ID of the subnet_ | _string_ | **_Optional <br/> (Default - null)_** |
| **_cidr\_block_** | _The CIDR block for the subnet_ | _string_ | **_Required_** |
| **_ipv6\_cidr\_block_** | _The IPv6 network range for <br/> the subnet, in CIDR notation_ | _string_ | **_Optional <br/> (Default - null)_** |
| **_map\_public\_ip\_on\_launch_** | _Specify true to indicate that <br/> instances launched into the subnet <br/> should be assigned a public IP address_ | _bool_ | **_Optional <br/> (Default - false)_** |
| **_assign\_ipv6\_address\_on\_creation_** | _Specify true to indicate that network interfaces <br/> created in the specified subnet should be <br/> assigned an IPv6 address_ | _bool_ | **_Optional <br/> (Default - false)_** |
| **_vpc\_id_** | _The VPC ID_ | _string_ | **_Required_** |
| **_tags_** | _A mapping of tags to assign to the resource_ | _map(string)_ | **_Required_** |



---


## _Outputs_

### _General_

_This module has the following outputs:_

* **_arn_**
* **_id_**


---

### _Usage_

_In order for the variables to be accessed at module level please use the syntax below:_

```tf
module.<module_name>.<output_variable_name>
```


_The output variable is able to be accessed through terraform state file using the syntax below:_

```tf
data.terraform_remote_state.<layer_name>.<output_variable_name>
```

---



## _Authors_

_Module maintained by Module maintained by the -_ **_Nitin Das_**
