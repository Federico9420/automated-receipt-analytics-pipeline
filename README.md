# Automated Receipt Analytics Pipeline

## 📌 Project Overview

This project is an end-to-end automation pipeline designed to extract, normalize, and analyze expense data from receipts and invoices using AI-driven document processing and business intelligence tools.

The system ingests receipt images via Telegram, converts semi-structured data into structured datasets using Large Language Models (LLMs), and delivers analytical insights through an interactive Power BI dashboard.

---

## 🎯 Business Problem

Expense tracking is often manual, fragmented, and prone to human error. Receipts and invoices typically contain semi-structured or unstructured data that is difficult to process automatically.

Common challenges include:

- Manual expense registration  
- Loss of financial visibility  
- Inconsistent vendor formats  
- Time-consuming reporting  

---

## 🧠 Solution

This pipeline automates the entire expense processing lifecycle, from ingestion to analytics.

The system:

- Receives receipt images via Telegram
- Parses documents asynchronously
- Extracts structured data using LLMs with JSON schema validation
- Normalizes line-item level data
- Stores analytics-ready records
- Generates insights through Power BI dashboards

---

## 🏗 Architecture Overview

Telegram Bot
↓
File Upload
↓
Document Parsing API
↓
LLM Structured Extraction
↓
Data Normalization
↓
Storage Layer
↓
Power BI Dashboard


---

## 🧰 Tech Stack

### Workflow & Automation
- n8n
- Telegram Bot API

### AI & Data Processing
- LlamaIndex Parsing API
- OpenAI LLM
- JSON Schema Validation

### Storage Layer
- Google Sheets

### Analytics & Visualization
- Power BI

---

## 🔄 Data Pipeline Flow

1. User uploads receipt image through Telegram  
2. Workflow downloads the document  
3. Parsing API processes document asynchronously  
4. LLM extracts structured data  
5. Items are normalized  
6. Data is stored in structured format  
7. Power BI consumes dataset for analytics  

---

## 📊 Example Data Schema

```json
{
  "Fecha": "DD-MM-YYYY",
  "Lugar": "Merchant Name",
  "MetodoDePago": "Payment Method",
  "Items": [
    {
      "Producto": "Item Name",
      "Cantidad": 1,
      "PrecioUnitario": 100,
      "Descuento": null,
      "Subtotal": 100
    }
  ]
}
⚙ Challenges & Learnings
Handling semi-structured financial documents

Designing schema validation for AI outputs

Normalizing line-item expense data

Managing ambiguous discount allocations

🚀 Future Improvements
SQL storage migration

Automated data validation layer

AI-based expense categorization

Real-time analytics

👤 Author
Federico Almonacid
Business Intelligence & Data Analytics

🔗 LinkedIn:
https://www.linkedin.com/in/federico-almonacid-a90bb9181/
