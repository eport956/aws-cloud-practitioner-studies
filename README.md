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
