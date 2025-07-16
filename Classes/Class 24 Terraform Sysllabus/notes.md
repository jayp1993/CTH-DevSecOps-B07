
---

## 📘 **Terraform Notes (Complete Syllabus)**

### **1. Introduction to Infrastructure as Code (IaC)**

* **What is IaC?** Automating infrastructure provisioning.
* **Tools:** Terraform, Ansible, ARM, CloudFormation.
* **Benefits:** Version control, repeatability, cost efficiency.

---

### **2. Terraform Basics**

* **What is Terraform?** Open-source IaC tool by HashiCorp.
* **Installation:** Download from [terraform.io](https://www.terraform.io), add to system path.
* **Providers:** Plugins to interact with cloud services (e.g., `azurerm`, `aws`, `google`).
* **Main Commands:**

  * `terraform init`: Initialize working directory.
  * `terraform plan`: Preview changes.
  * `terraform apply`: Apply changes.
  * `terraform destroy`: Delete resources.
  * `terraform fmt`: Format code.
  * `terraform validate`: Validate syntax.

---

### **3. Terraform Configuration Language**

* **HCL (HashiCorp Configuration Language):** Declarative syntax.
* **Basic Syntax Elements:**

  * **Resource Block**: Defines infrastructure

    ```hcl
    resource "azurerm_resource_group" "example" {
      name     = "my-rg"
      location = "East US"
    }
    ```
  * **Variables & Outputs**

    ```hcl
    variable "location" {}
    output "rg_name" {
      value = azurerm_resource_group.example.name
    }
    ```
  * **Data Source**: Fetch existing resources.
  * **Providers**: Declare and configure.

---

### **4. Variables in Terraform**

* **Types:** string, number, bool, list, map, object.
* **Variable Files:** `terraform.tfvars`, `*.auto.tfvars`.
* **Input Variables**: Accept user input.
* **Output Values**: Return useful data.
* **Default Values** and **Description** support.

---

### **5. State Management**

* **Terraform State (`terraform.tfstate`)**:

  * Keeps track of resources created.
  * Should be managed securely.
* **Commands:**

  * `terraform show`
  * `terraform state list`
  * `terraform state show`
* **Remote State:** Use with backends like Azure Storage, S3, etc.

---

### **6. Backends**

* **Local Backend (default)**: Saves state on local machine.
* **Remote Backends**: Azure Blob, AWS S3, Terraform Cloud.
* **Example: Azure Backend**

  ```hcl
  backend "azurerm" {
    storage_account_name = "tfstate123"
    container_name       = "tfstate"
    key                  = "terraform.tfstate"
  }
  ```

---

### **7. Modules in Terraform**

* **What is a Module?** Reusable, self-contained Terraform code.
* **Structure:**

  * `main.tf`, `variables.tf`, `outputs.tf`
* **Calling Modules:**

  ```hcl
  module "vnet" {
    source = "./modules/vnet"
    name   = "myvnet"
  }
  ```
* **Registry Modules:** [registry.terraform.io](https://registry.terraform.io)

---

### **8. Terraform Functions**

* Built-in functions: `concat()`, `length()`, `lookup()`, `element()`, etc.
* Used to transform or calculate values dynamically.

---

### **9. Conditional & Looping Constructs**

* **Conditionals:** `count`, `for_each`, `if-else` expressions.
* **Loops:**

  ```hcl
  resource "azurerm_subnet" "example" {
    for_each = var.subnets
  }
  ```

---

### **10. Workspaces**

* **Used for managing multiple environments (dev, test, prod).**
* Commands:

  * `terraform workspace list`
  * `terraform workspace new dev`
  * `terraform workspace select dev`

---

### **11. Terraform Provisioners**

* Used to run scripts (not recommended for production).
* Types: `local-exec`, `remote-exec`.

---

### **12. Terraform Cloud & Enterprise (optional)**

* **Terraform Cloud**: Managed service for remote runs, team collaboration.
* **Features:** VCS integration, remote state, variable sets.

---

### **13. Real-World Use Cases**

* **Azure Resource Provisioning**
* **Multi-tier architecture deployment**
* **VM + VNet + NSG + Subnet creation**
* **Azure DevOps integration with Terraform**
* **CI/CD pipelines using Terraform**

---

### **14. Terraform Best Practices**

* Use remote state with locking.
* Use modules for reusability.
* Follow naming conventions.
* Store secrets in Key Vault or Vault.
* Use `.terraformignore` and `terraform fmt`.

---

### **15. Interview Preparation Topics**

* Terraform vs ARM templates
* Lifecycle rules
* Difference between `count` and `for_each`
* Module reuse
* Handling sensitive variables
* State file security

---

