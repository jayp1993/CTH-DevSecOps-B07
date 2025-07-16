

# 🚀 Terraform with VS Code + GitHub Copilot — Smart IaC Development

---

## 📌 Introduction

Terraform is an Infrastructure as Code (IaC) tool to manage cloud infrastructure. VS Code and GitHub Copilot together provide a powerful, AI-assisted development environment to write Terraform code faster and more efficiently.

---

## 🛠️ Setup Guide

### 1. Install VS Code

* Download from: [https://code.visualstudio.com](https://code.visualstudio.com)

### 2. Install Extensions in VS Code

* ✅ **Terraform Extension** (by HashiCorp)
* ✅ **GitHub Copilot** (requires a GitHub Copilot subscription)
* ✅ **Prettier** (for code formatting)
* ✅ **Bracket Pair Colorizer** (optional, improves readability)

### 3. Configure Terraform

```bash
# Install Terraform CLI
https://developer.hashicorp.com/terraform/downloads
```

* Verify installation:

```bash
terraform -v
```

---

## ⚙️ Connect Copilot to VS Code

### Steps:

1. Sign in to GitHub in VS Code.
2. Enable GitHub Copilot extension.
3. Check if suggestions work:

   * Type `resource "azurerm_` and Copilot will auto-suggest resources.

---

## 💡 Copilot + Terraform: Smart Coding Examples

### 👉 Create a Virtual Network (VNet)

Start typing:

```hcl
resource "azurerm_virtual_network"
```

Copilot Suggestion:

```hcl
resource "azurerm_virtual_network" "vnet" {
  name                = "myVnet"
  location            = azurerm_resource_group.rg.location
  resource_group_name = azurerm_resource_group.rg.name
  address_space       = ["10.0.0.0/16"]
}
```

### 👉 Create a Virtual Machine

Start typing:

```hcl
resource "azurerm_virtual_machine"
```

Copilot will likely suggest:

```hcl
resource "azurerm_virtual_machine" "vm" {
  name                  = "vm-example"
  location              = azurerm_resource_group.rg.location
  resource_group_name   = azurerm_resource_group.rg.name
  network_interface_ids = [azurerm_network_interface.nic.id]
  vm_size               = "Standard_DS1_v2"

  os_profile {
    computer_name  = "vmexample"
    admin_username = "azureuser"
    admin_password = "P@ssword123!"
  }

  os_profile_linux_config {
    disable_password_authentication = false
  }

  storage_image_reference {
    publisher = "Canonical"
    offer     = "UbuntuServer"
    sku       = "18.04-LTS"
    version   = "latest"
  }

  storage_os_disk {
    name              = "osdisk"
    caching           = "ReadWrite"
    create_option     = "FromImage"
    managed_disk_type = "Standard_LRS"
  }
}
```

---

## ⚡ Copilot Pro Tips

* 💡 Use comments to get better suggestions:

  ```hcl
  # Create an Azure resource group
  resource "azurerm_resource_group" "rg" {
  ```
* 🧠 Use Copilot to learn unfamiliar syntax.
* ✨ Use `//` or `#` to write your intent in English — Copilot understands!

---

## ✅ Benefits of Copilot + Terraform

| Feature         | Benefit                           |
| --------------- | --------------------------------- |
| ⚡ Speed         | Autocomplete repetitive blocks    |
| 🧠 Intelligence | Learns from your coding style     |
| 🧰 Productivity | Less context switching to docs    |
| 📘 Learning     | Teaches resource syntax as you go |

---

## 🧪 Terraform Commands Cheat Sheet

```bash
terraform init      # Initialize working directory
terraform plan      # Preview infrastructure changes
terraform apply     # Apply configuration changes
terraform destroy   # Destroy all managed infrastructure
terraform fmt       # Format the code
terraform validate  # Validate the configuration
```

---

## 🧱 Real-World Project Structure

```bash
terraform/
├── main.tf
├── variables.tf
├── outputs.tf
├── terraform.tfvars
├── provider.tf
```

---

## 📚 Best Practices

* Split code into modules for reuse.
* Store sensitive data in Azure Key Vault or use `vault_provider`.
* Use `.tfvars` files to manage environments.
* Use GitHub Copilot for boilerplate, but always **review suggestions**.
* Maintain version control using Git and GitHub.

---
