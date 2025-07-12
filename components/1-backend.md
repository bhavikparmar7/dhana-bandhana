# Backend API (NestJS)

The backend is built using **NestJS**, a TypeScript-based framework that powers the core business logic of the Dhana Bandhana project.

---

## Overview

* Exposes a REST API consumed by the React frontend
* Secures requests via Firebase ID tokens (phone authentication)
* Handles user accounts, file metadata, transaction tagging, and finalization
* Connects to **MongoDB Atlas** and **PostgreSQL (RDS)**

---

## Tech Stack

* **NestJS** (TypeScript)
* **TypeORM** for PostgreSQL
* **Mongoose** for MongoDB
* **Firebase Admin SDK** for token verification
* **AWS SDK (S3)** for file management

---

## Authentication

* Firebase Phone Auth used on frontend
* Frontend passes the **Firebase ID Token** to backend
* Backend verifies the token using `firebase-admin` SDK

---

## Databases

### MongoDB Atlas

* Stores raw files data uploaded by user
* Stores raw transaction data parsed by the processor

### PostgreSQL (RDS)

* Finalized, normalized transactions for reports and analytics
* SQL-friendly queries and schema enforcement

---

## Deployment

* Hosted on an **Amazon EC2 instance** in public subnet
* Reverse proxy via **Nginx** with HTTPS from **Let's Encrypt (Certbot)**
* Connected to domain: `api.dhanabandhana.in`
* Managed using **PM2** for auto-restarts

---

## 🔗 Additional Details in Repo

* [dhana-bandhana-nestjs](https://github.com/bhavikparmar7/dhana-bandhana-nestjs)
