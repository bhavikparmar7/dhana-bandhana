# Dhana Bandhana ₹💰₹

A personal finance web platform that allows users to upload and categorize their bank and credit card statements, extract transaction data, and generate insights via a secure and scalable cloud-based system.

## 🌐 Live Site

* [https://www.dhanabandhana.in](https://www.dhanabandhana.in)

## 🔗 Linked Repositories

* [Backend (NestJS)](https://github.com/bhavikparmar7/dhana-bandhana-nestjs)
* [Processor (Python)](https://github.com/bhavikparmar7/dhana-niskarsaka-python)
* [Frontend (React)](https://github.com/bhavikparmar7/dhana-pradarsana-react)

## 📦 Project Components

### 1. **Backend API** (NestJS)
### 2. **Python Processor**
### 3. **Frontend** (React + Firebase)
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

## 🔖 Additional Resources

* Detailed component docs under `/components`
* Diagrams under `/diagrams`
