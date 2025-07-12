# Infrastructure

This project is hosted entirely on the cloud with a combination of AWS services and GitHub for version control.

---

## ☁️ Components Used

### ✅ S3 (Simple Storage Service)

* Stores uploaded bank and credit card statement files
* Used to host the frontend React app (static website hosting)

### ✅ SQS (Simple Queue Service)

* Handles communication between backend and Python processor
* Message is sent on new file upload to trigger async processing

### ✅ EC2 (Elastic Compute Cloud)

* Backend NestJS API hosted on one EC2 instance
* Python processor hosted on a separate EC2 instance
* Node.js and Python environments configured manually

### ✅ RDS (Relational Database Service)

* PostgreSQL used for finalized transaction storage and analytics
* Connection secured over SSL

### ✅ MongoDB Atlas

* Stores raw files parsed transactions before finalization
* Used for fast JSON-like access and iteration

### ✅ CloudFront

* Global content delivery network for the frontend static app
* Linked to S3 bucket with HTTPS using ACM

### ✅ ACM (AWS Certificate Manager)

* Manages TLS/SSL certificates for HTTPS
* Used with CloudFront and backend EC2 (Nginx)

### ✅ Hostinger

* Hostinger DNS is used to manage domains
* Points `api.dhanabandhana.in` and `www.dhanabandhana.in` to the correct services

---

## Security Measures

* IAM roles scoped to only required permissions
* RDS and MongoDB are accessible only from whitelisted IPs or VPC
* HTTPS enforced across frontend and backend
* EC2 backend protected by security groups and domain-only access

---

## Domains

* `www.dhanabandhana.in` → React frontend (via CloudFront)
* `api.dhanabandhana.in` → NestJS backend (via EC2 + Nginx)
