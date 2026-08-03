# 🧾 InvoiceIQ AI – Intelligent Invoice Processing & Approval

An AI-powered invoice processing automation built using **n8n**, **Google Gemini 2.5 Flash**, **Google Sheets**, **Gmail**, and **Telegram**.

InvoiceIQ automatically extracts structured data from invoice PDFs received via email, detects duplicate invoices, stores validated records, and sends instant alerts for duplicate submissions.

---

# 🚀 Features

- 📧 Automatically monitors Gmail for incoming invoice emails
- 🤖 Extracts invoice details using Google Gemini 2.5 Flash
- 📄 Supports PDF invoice processing
- 💱 Auto-detects invoice currency (INR, USD, EUR, GBP)
- 📊 Extracts:
  - Invoice Number
  - Vendor
  - Invoice Date
  - Due Date
  - Currency
  - Subtotal
  - Tax
  - Total
  - Payment Terms
- 📈 Generates AI Confidence Score
- 🔍 Detects duplicate invoices using Google Sheets
- 📩 Sends Telegram alerts when duplicate invoices are detected
- 💾 Stores validated invoices in Google Sheets
- ⚠️ Handles invoices with missing fields gracefully

---

# 🛠 Tech Stack

- n8n
- Google Gemini 2.5 Flash
- Gmail Trigger
- Google Sheets
- Telegram Bot API

---

# 🏗 Workflow Architecture

```text
Gmail Trigger
      │
      ▼
Gemini 2.5 Flash
(Document Analysis)
      │
      ▼
AI Invoice Parser
      │
      ▼
Structured JSON Output
      │
      ▼
Google Sheets
(Check Duplicate)
      │
      ▼
        IF
   ┌─────────────┐
   │             │
Duplicate      New Invoice
   │             │
Telegram      Save to
 Alert      Google Sheets
```

---

# 📊 Extracted Fields

The workflow extracts the following information:

- Invoice Number
- Vendor
- Invoice Date
- Due Date
- Currency
- Subtotal
- Tax
- Total
- Payment Terms
- Confidence Score
- Processing Status

---

# 🔄 Workflow

1. Gmail detects a new email containing a PDF invoice.
2. Google Gemini analyzes the invoice document.
3. AI extracts structured invoice information.
4. Invoice number is checked against Google Sheets.
5. If duplicate:
   - Telegram notification is sent.
6. If new:
   - Invoice is stored in Google Sheets.
7. Processing completes automatically.

---
