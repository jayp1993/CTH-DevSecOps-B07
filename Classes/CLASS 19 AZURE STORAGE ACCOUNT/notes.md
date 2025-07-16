

### 🔹 **Azure Storage Account – Notes**

#### ✅ **Overview**

* A **Storage Account** provides a **unique namespace** in Azure for storing data.
* It is a **scalable** and **durable** solution for storing different types of data.
* Supports **Blobs**, **Files**, **Queues**, **Tables**, and **Disks**.

---

#### 🏷️ **Types of Storage Accounts**

* **General-purpose v2 (GPv2)** – Supports all storage types (recommended).
* **General-purpose v1 (GPv1)** – Legacy; limited features.
* **Blob Storage** – For only blob (object) storage.
* **FileStorage** – Optimized for Azure Files.
* **BlockBlobStorage** – Premium performance for block blobs.

---

#### 🗂️ **Storage Services**

1. **Blob Storage**

   * Used to store unstructured data (e.g., images, videos, documents).
   * Types: **Block Blob**, **Append Blob**, **Page Blob**.
2. **File Storage (Azure Files)**

   * Fully managed file shares accessible via **SMB/NFS** protocols.
3. **Queue Storage**

   * Stores messages for **decoupled** communication between applications.
4. **Table Storage**

   * NoSQL key-value store for structured data.
5. **Disk Storage**

   * Persistent disks for **Azure Virtual Machines**.

---

#### 🔒 **Security**

* Supports **Azure Active Directory (AAD)** and **Shared Access Signatures (SAS)**.
* **Encryption at rest** and **in-transit** enabled by default.
* **Private Endpoints** for secure access.

---

#### 🌍 **Redundancy Options**

* **LRS (Locally Redundant Storage)** – 3 copies in a single region.
* **ZRS (Zone-Redundant Storage)** – Replication across zones in one region.
* **GRS (Geo-Redundant Storage)** – Region + paired region replication.
* **GZRS (Geo-Zone-Redundant Storage)** – ZRS + secondary region.

---

#### 📊 **Performance Tiers**

* **Standard** – HDD-based; low cost.
* **Premium** – SSD-based; high performance.

---

#### 🧾 **Access Tiers (Blobs)**

* **Hot** – Frequent access.
* **Cool** – Infrequent access.
* **Archive** – Rare access, high latency, cheapest.

---

#### 🧰 **Common Use Cases**

* Hosting static websites.
* Backup and disaster recovery.
* Data archival.
* Content delivery (e.g., media files).
* Application logging and telemetry.

-