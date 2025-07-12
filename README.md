# Dhana Bandhana ₹

A personal finance web platform that allows users to upload bank/credit card statements, extract transaction data, categorize their transactions, and generate balance sheet via a secure and scalable cloud-based system.

## 🌐 Live Site

* [https://www.dhanabandhana.in](https://www.dhanabandhana.in) — *Request to view on Desktop Web for seamless experience*

## 🔗 Linked Repositories

* [Backend (dhana-bandhana-nestjs)](https://github.com/bhavikparmar7/dhana-bandhana-nestjs)
* [Processor (dhana-niskarsaka-python)](https://github.com/bhavikparmar7/dhana-niskarsaka-python)
* [Frontend (dhana-pradarsana-react)](https://github.com/bhavikparmar7/dhana-pradarsana-react)

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
5. **User resolves (categorizes) raw transaction** via frontend and saved in **PostgresDB**
6. **Frontend fetches data** from backend APIs for display

## 🔖 Additional Resources

* Detailed component docs under `/components`
* Diagrams under `/diagrams`
* UI Screenshots under `/screenshots`
* Sample usage instructions under `/sample-user` for anyone who wants to try the website
