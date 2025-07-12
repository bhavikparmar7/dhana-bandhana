# Python Processor

The Python processor handles the core logic of extracting transaction data from uploaded bank and credit card statements. It is triggered by **SQS messages** and processes files stored in **S3**.

---

## Purpose

* Polls SQS for messages related to new file uploads
* Downloads files from S3
* Parses PDF or Excel statements
* Inserts raw transactions into **MongoDB Atlas**
* Usage of **DLQ** If any exception during process

---

## Tech Stack

* **Python 3.9** (Amazon Linux default)
* **boto3** for AWS (S3, SQS)
* **pdfplumber** for PDF parsing
* **pandas** for tabular data handling
* **pymongo** for MongoDB integration
* **python-dotenv** for config management
* Managed using **pm2** for auto-restart and logging

---

## Deployment Details

* Hosted on **EC2** in public subnet (for now)
* Installed and run inside a Python `venv`
* Started using `pm2 start main.py`
* Polls SQS with `WaitTimeSeconds=10` for efficiency

---

## 🔗 Additional Details

* [dhana-niskarsaka-python](https://github.com/bhavikparmar7/dhana-niskarsaka-python) — *"niskarsaka" means "extraction" in Sanskrit*
