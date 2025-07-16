
---

## 🚀 **Terraform Providers – Complete Notes**

---

### 🔷 What is a Provider?

> A **Terraform Provider** is a plugin that acts as a **bridge between Terraform and an external API** (e.g., Azure, AWS, GCP).
> It lets Terraform **create, read, update, and delete** (CRUD) resources on that platform.

📌 Think of it like a **driver** that connects Terraform with cloud services.

---

### 🌐 Popular Providers

| Provider      | Name Used    | Platform              |
| ------------- | ------------ | --------------------- |
| 🌩️ Azure     | `azurerm`    | Microsoft Azure       |
| ☁️ AWS        | `aws`        | Amazon Web Services   |
| 🌍 GCP        | `google`     | Google Cloud Platform |
| 🐳 Kubernetes | `kubernetes` | K8s Clusters          |
| 🐙 GitHub     | `github`     | GitHub Repos          |

> ⚡ Thousands of providers are available on the [Terraform Registry](https://registry.terraform.io/).

---

### 📦 Basic Provider Block

```hcl
provider "azurerm" {
  features {}

  subscription_id = "your-sub-id"
  client_id       = "your-client-id"
  client_secret   = "your-secret"
  tenant_id       = "your-tenant-id"
}
```

✅ This tells Terraform **which cloud to use** and **how to authenticate**.

---

### 🔁 Using Multiple Providers (Alias)

> Useful when you want to deploy to **multiple regions** or **multiple subscriptions**.

```hcl
provider "azurerm" {
  alias           = "east"
  features        = {}
  subscription_id = "sub-east"
}

provider "azurerm" {
  alias           = "west"
  features        = {}
  subscription_id = "sub-west"
}

resource "azurerm_resource_group" "rg_east" {
  provider = azurerm.east
  name     = "rg-east"
  location = "East US"
}
```

---

### 📌 Specifying Provider Version

Use `required_providers` block to **lock versions**:

```hcl
terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "~> 3.50"
    }
  }
}
```

🔒 This ensures your configuration works with **known and tested versions**.

---

### ⚙️ Initializing Providers

Run this command:

```bash
terraform init
```

🔽 Downloads the required provider plugins
✅ Prepares your working directory for deployment

---

### 🛠️ Custom Providers

You can even build your **own provider** (in Go language) for unsupported services!

---

### 🧠 Quick Recap

| Concept              | Purpose                                      |
| -------------------- | -------------------------------------------- |
| `provider` block     | Configure API access                         |
| `alias`              | Multiple configurations of the same provider |
| `required_providers` | Version control                              |
| `terraform init`     | Downloads providers                          |
| Registry             | Find new providers easily                    |

---

L