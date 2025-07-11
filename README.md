# Dhana Bandhana ₹💰₹

A personal finance web platform that allows users to upload and categorize their bank and credit card statements, extract transaction data, and generate insights via a secure and scalable cloud-based system.

## 🔗 Linked Repositories

* [Backend (NestJS)](https://github.com/bhavikparmar7/dhana-bandhana-nestjs)
* [Processor (Python)](https://github.com/bhavikparmar7/dhana-niskarsaka-python)
* [Frontend (React)](https://github.com/bhavikparmar7/dhana-pradarsana-react)

## 🌐 Live Site

* [https://www.dhanabandhana.in](https://www.dhanabandhana.in)

## 📦 Project Components

### 1. **Backend API** (NestJS)

* Handles user auth, file metadata, categorization, and reporting
* Connected to MongoDB Atlas and PostgreSQL (RDS)
* Hosted on EC2 with Nginx + HTTPS (Certbot)
* Domain: `api.dhanabandhana.in`

### 2. **Python Processor**

* Extracts transaction data from uploaded PDF/CSV files
* Listens to SQS, downloads from S3, parses, and stores in MongoDB
* Hosted on a separate EC2 using `pm2` for persistence

### 3. **Frontend** (React + Firebase)

* React app with TailwindCSS and shadcn/ui
* Firebase Phone Authentication
* Hosted on S3 + CloudFront
* Domain: `www.dhanabandhana.in`

### 4. **Infrastructure**

* EC2: For backend and processor compute
* S3 Buckets: For raw file uploads
* SQS: Triggers the processor
* MongoDB Atlas: Intermediate processing state
* RDS PostgreSQL: Final structured data for reporting
* Firebaase: For phone auth
* Hostinger DNS: Domain management
* ACM: TLS certificate management

## 🔹 Usage Flow

1. **User uploads statement** via frontend
2. **File saved to S3**, message sent to SQS
3. **Python processor** picks message, parses file
4. Raw Transactions saved to **MongoDB**
5. **User resolves raw transaction** via frontend and saved in **PostgresDB**
6. **Frontend fetches data** from backend APIs for display

## 🔖 Reference Materials

* Detailed component docs under `/components`
* Diagrams under `/diagrams`
* Full setup guide for local + cloud environments
