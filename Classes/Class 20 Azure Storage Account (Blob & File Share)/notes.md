
---

## 🌩️ **Azure Storage Account – Complete Notes**

### 🔹 What is Azure Storage Account?

Azure Storage Account is a **cloud-based storage solution** provided by Microsoft that enables you to store a wide variety of data types—structured, semi-structured, and unstructured—with high **durability, availability, and scalability**.

---

## 🧱 Types of Azure Storage Accounts

| Type                   | Description                                                                 |
| ---------------------- | --------------------------------------------------------------------------- |
| **GPv2 (Recommended)** | Supports blobs, files, queues, and tables with all latest features.         |
| **GPv1 (Legacy)**      | Older version, limited features. Use GPv2 instead.                          |
| **Blob Storage**       | Specialized for blob data. (Use GPv2 instead.)                              |
| **Premium Storage**    | SSD-based, high-performance storage (used for VM disks and fast workloads). |

---

## 📦 **Blob Storage – Store Unstructured Data**

### ✅ **What is a Blob?**

* Blob = **Binary Large Object**
* Used to store **images, videos, documents, backups**, logs, and more.

### 🧊 **Blob Storage Tiers**

| Tier        | Use Case                   | Cost      | Access Speed    |
| ----------- | -------------------------- | --------- | --------------- |
| **Hot**     | Frequently accessed data   | 💰 High   | ⚡ Fast          |
| **Cool**    | Infrequently accessed data | 💸 Lower  | ⚠️ Moderate     |
| **Archive** | Rarely accessed data       | 💵 Lowest | 🐢 Slow (hours) |

### 🧱 **Types of Blobs**

* **Block Blob** – Large files like videos and images.
* **Append Blob** – Write-heavy operations like logging.
* **Page Blob** – VM disks (supports random read/write).

### 📁 **Blob Containers**

* Logical group of blobs (like a folder)
* Access levels:

  * 🔒 Private (default)
  * 👁 Blob (anonymous read blob)
  * 📂 Container (anonymous read blob + list)

### 🔐 **Access Methods & Security**

* Azure Portal, CLI, PowerShell, SDKs, REST API
* **Access Options:**

  * Shared Access Signature (SAS)
  * Azure AD-based RBAC
  * Access Keys (Primary/Secondary)

---

## 📂 **Azure File Share – Cloud-based SMB/NFS File Storage**

### ✅ **What is Azure File Share?**

A **fully managed file share** service in Azure that supports **SMB, NFS, and REST API** access. You can **mount it like a network drive** on your Windows, Linux, or macOS machine.

### 💡 **Key Features**

* 🧳 Lift-and-shift file-based apps to Azure
* 🖥 Mount as network drive (Windows/Linux)
* 🔁 Azure File Sync for hybrid scenarios
* 📈 Scalable up to **100 TiB**

### 🚀 **Performance Tiers**

| Tier         | Description                            | Backing Storage |
| ------------ | -------------------------------------- | --------------- |
| **Standard** | General purpose, budget friendly       | HDD             |
| **Premium**  | High IOPS and low latency requirements | SSD             |

### 🔐 **Authentication Options**

* Storage Account Key 🔑
* Azure AD DS 🏢
* Azure AD RBAC 🔐 (preview)

### 🛡 **Backup & Recovery**

* **Azure Backup** integration for file shares
* **Snapshot support** for point-in-time recovery

---

## 🎯 **Common Use Cases**

### 📦 Blob Storage

* Media content (videos, images)
* App and system backups
* Big data analytics
* Static website hosting 🌐

### 📁 File Share

* Shared file storage for apps
* Hybrid cloud file sync (Azure File Sync)
* Shared config files for VMs and containers

