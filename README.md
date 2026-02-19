# 🔐 SecureCart – Secure AWS Cloud Architecture (Security Pillar)

SecureCart is a **security-focused AWS cloud architecture project** designed to demonstrate how a real-world e-commerce application can be deployed using **AWS Security Pillar best practices**, while staying within the **AWS Free Tier**.

This project focuses on **network isolation, controlled access, and defense-in-depth**, not on application code.

---

## 📌 Project Objective

The goal of this project is to:
- Design a **secure and scalable AWS architecture**
- Prevent direct public access to critical resources
- Control traffic flow using AWS networking components
- Implement **least-privilege access**
- Document everything for learning, reference, and interviews

---

## 🧱 Architecture Overview

(architecture-diagram.png)


### Traffic Flow
User → AWS WAF → Application Load Balancer → EC2 (Private Subnet) → RDS (Private Subnet)
 
---

## 🛠 AWS Services Used & Why

### 🌐 Amazon VPC
- Provides an isolated network for all resources
- Full control over IP addressing and routing
- Foundation of the secure architecture

---

### 🔀 Subnets
- **Public Subnet**
  - Bastion Host
  - Application Load Balancer
- **Private Subnet**
  - Application EC2 instance
  - RDS database

👉 Keeps backend resources completely hidden from the internet

---

### 🧭 Route Tables
- Public route table → Internet Gateway
- Private route table → NAT Gateway

👉 Allows **outbound internet access only**, no inbound exposure

---

### 💻 Amazon EC2
- **App Server**
  - No public IP
  - Accessible only through Bastion
- **Bastion Host**
  - Acts as a secure entry point
  - SSH allowed only from my IP

---

### 🛡 Security Groups
- Bastion SG → SSH from my IP only
- App SG → SSH only from Bastion SG
- RDS SG → MySQL access only from App SG

👉 Enforces **least privilege access**

---

### 🗄 Amazon RDS (MySQL)
- Deployed in private subnet
- Public access disabled
- Accessible only from App Server

👉 Protects sensitive database data

---

### 🔥 AWS WAF
- Protects application from common web attacks
- Filters malicious traffic before it reaches EC2

---

### 📦 Amazon S3
- Used for storing application assets
- Public access completely blocked

---

## 📸 Screenshots

This repository includes **real AWS Console screenshots** showing:
- VPC and subnet setup
- Route tables
- EC2 instances
- Security groups
- RDS configuration
- WAF rules
- S3 permissions

Screenshots are organized inside the `screenshots/` folder.

---

## 📄 Documentation

A detailed explanation of:
- Architecture design
- Security decisions
- Service configuration
- Traffic flow

is available in the PDF:

📘 **SecureCart – Redesigning for Enterprise Security on AWS (Security Pillar)**

---

## 🎯 What I Achieved

- Designed a **production-style secure AWS architecture**
- Implemented **network isolation**
- Used **defense-in-depth** principles
- Followed AWS Security Pillar guidelines
- Built everything using **AWS Free Tier**
- Documented the system clearly for learning and interviews

---

## 🚀 Who This Project Is For

- AWS learners
- Cloud security beginners
- Interview preparation
- Portfolio showcase
- Future reference

---

## 👨‍💻 Author

**Arush Patel**  
AWS Certified Solutions Architect – Associate  

---

## 📜 License

This project is open for learning and reference purposes.
