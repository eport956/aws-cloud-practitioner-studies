# aws-cloud-practitioner-studies
Notes, concepts, and hands-on labs for the AWS Certified Cloud Practitioner certification.

## Section 1: Introduction to Cloud ☁️
Cloud computing is the on-demand delivery of compute power, database, storage, and other IT resources via the internet with pay-as-you-go pricing.

**Key Benefits:**
* **Go Global in minutes:** Deploy applications worldwide.
* **Stop guessing capacity:** Scale up/down as needed.
* **Trade Capital Expense for Variable Expense:** Pay only for what you consume.

---

## Section 2: AWS Global Infrastructure 🌎
AWS is organized into a massive global network. Here is how it works:

### 1. AWS Regions
* **What it is:** A physical location in the world where AWS has multiple data centers (e.g., North Virginia, São Paulo).
* **The Goal:** You choose a region close to your users to reduce delays and comply with local laws.

### 2. Availability Zones (AZ)
* **What it is:** Think of an AZ as a "Fortress". Each Region has at least 3 AZs. 
* **The Goal:** They are physically separated from each other. If one AZ has a flood or power outage, the others keep your application running. **This is High Availability.**

### 3. Edge Locations (Points of Presence)
* **What it is:** These are like "Mini Data Centers" spread all over the globe (much more numerous than Regions).
* **The Goal:** They store a copy of your content (videos, images) closer to the final user. 
* **Analogy:** If your server is in the USA (Region) and your user is in Bahia, the user doesn't have to "travel" to the USA to get a photo. They get it from an **Edge Location** in Brazil. This is what we call **Low Latency** (high speed).

---

## Section 3: The Shared Responsibility Model 🛡️
Security and Compliance is a shared responsibility between AWS and the customer.

* **AWS (Security OF the Cloud):** Responsible for the physical infrastructure (Hardware, Software, Facilities).
* **Customer (Security IN the Cloud):** Responsible for data encryption, Identity Access Management (IAM), and network firewall configuration.

  ---

## Section 4: IAM - Identity and Access Management 🔐

IAM is the administrative service that manages who can access your AWS environment and what they can do.

### 1. The Root User vs. IAM Users
* **Root User:** The account creator. It has "God Mode" (full access). 
    * **Best Practice:** Use it ONLY for initial setup and emergency tasks. **Never use it for daily tasks.**
* **IAM User:** Created for daily work. 
    * **IAM Admin:** You can create an IAM User with **Full Administrator Permissions**. This user can manage everything (create users, groups, restrict accounts, etc.) while the Root account stays protected.
    * **Hierarchy:** From this Admin user, you can create other users with equal or lesser permissions based on their job functions.

### 2. IAM Groups & Roles
* **Groups:** A collection of users (e.g., "Finance", "Devs"). It's easier to manage permissions for a group than for each individual.
* **Roles:** Think of a Role as a **temporary hat** that an AWS service or a user wears to perform a specific task.
    * **Deep Dive into Roles:** Roles do not have passwords or keys. They use temporary security tokens.
    * **Example 1 (Service Role):** You have an **EC2 Instance** (virtual server) that needs to upload files to an **S3 Bucket** (storage). Instead of putting your password inside the server, you give the EC2 a **Role** that allows it to talk to S3.
    * **Example 2 (Cross-Account):** You can create a Role to allow a user from another AWS account to access resources in your account securely.

### 3. Security Protocols
* **Principle of Least Privilege:** Users should only have the permissions they strictly need.
* **MFA (Multi-Factor Authentication):** **Mandatory.** An extra layer of security. You should enable this for the Root User and all IAM Users.

### 4. Ways to Access AWS
1. **AWS Management Console:** Web Browser interface.
2. **AWS CLI (Command Line Interface):** Terminal access using **Access Keys**.
3. **AWS SDK:** Programmatic access for applications (code).
