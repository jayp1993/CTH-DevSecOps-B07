

# Terraform Study Notes

## 1. What is Terraform?

* **Terraform** is an open-source **Infrastructure as Code (IaC)** tool developed by **HashiCorp**.
* It enables users to define and provision infrastructure using a declarative configuration language known as **HashiCorp Configuration Language (HCL)**.
* Terraform supports multiple cloud providers, including **AWS**, **Azure**, **Google Cloud**, and more, making it a **cloud-agnostic** tool.
* Key features include:

  * **Declarative Configuration**: Users define the desired state of infrastructure, and Terraform manages the execution plan to reach that state.
  * **Execution Plans**: Terraform generates an execution plan to preview changes before applying them.
  * **Resource Graphs**: It builds a graph of all resources, enabling parallel execution and efficient resource management.
  * **Change Automation**: Automates the process of changing infrastructure with minimal human intervention.

## 2. Core Terraform Workflow

Terraform's workflow consists of three primary steps:

1. **Write**: Define infrastructure resources in `.tf` files using HCL.
2. **Plan**: Run `terraform plan` to preview the changes Terraform will make to match the desired state.
3. **Apply**: Execute `terraform apply` to apply the planned changes and provision the infrastructure.

This workflow ensures that infrastructure changes are predictable and manageable.&#x20;

## 3. Terraform Architecture

* **Terraform Core**: The engine that reads configuration files, manages the state, and executes plans to apply changes.
* **Providers**: Plugins that interact with APIs of cloud providers and other services (e.g., AWS, Azure, Kubernetes).
* **Configuration Files**: Written in HCL, these files define the desired infrastructure resources.
* **State Management**: Terraform maintains a state file (`terraform.tfstate`) to map real-world resources to your configuration, track metadata, and improve performance.



## 4. Key Terraform Commands

* `terraform init`: Initializes a working directory containing Terraform configuration files.
* `terraform plan`: Creates an execution plan, showing what actions Terraform will take.
* `terraform apply`: Applies the changes required to reach the desired state of the configuration.
* `terraform destroy`: Destroys the infrastructure managed by Terraform.
* `terraform validate`: Validates the syntax of the configuration files.
* `terraform fmt`: Formats the configuration files to a canonical format.
* `terraform state`: Advanced command to inspect and modify the state.

## 5. Terraform Configuration Language (HCL)

* **Resources**: The most important element in the Terraform language; each resource block describes one or more infrastructure objects.

  ```hcl
  resource "aws_instance" "example" {
    ami           = "ami-0c55b159cbfafe1f0"
    instance_type = "t2.micro"
  }
  ```
* **Variables**: Define input values to make configurations more flexible.

  ```hcl
  variable "instance_count" {
    type    = number
    default = 2
  }
  ```
* **Outputs**: Define values that will be displayed to the user after `terraform apply`.

  ```hcl
  output "instance_ip" {
    value = aws_instance.example.public_ip
  }
  ```
* **Modules**: Containers for multiple resources that are used together. Modules can be used to create lightweight abstractions, so that you can describe your infrastructure in terms of its architecture, rather than directly in terms of physical objects.

## 6. State Management

* Terraform uses a **state file** to keep track of the resources it manages.
* The state file maps Terraform resources to real-world infrastructure.
* It is critical to manage state files securely, especially when working in teams.
* **Remote backends** (e.g., AWS S3, HashiCorp Consul) can be used to store state files remotely and enable collaboration.

## 7. Best Practices

* **Use Version Control**: Store your Terraform configurations in a version control system like Git.
* **State File Security**: Protect your state files, as they may contain sensitive information.
* **Modularize Configurations**: Use modules to organize and reuse code.
* **Use Variables and Outputs**: Make your configurations flexible and outputs informative.
* **Regularly Run `terraform plan`**: Always preview changes before applying them to avoid unintended consequences.

---
