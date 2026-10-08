# 💰 Personal FinAI — AI-Powered Personal Finance Dashboard

An AI-powered personal finance application built as part of the **Samsung Innovation Campus (SIC) Generative AI Capstone Project**.

Personal FinAI helps users analyze their expenses, automatically extract information from receipts, categorize transactions using Generative AI, visualize spending patterns, simulate SIP-based wealth growth, and generate an AI-powered financial health assessment.

---

## 📌 Project Overview

Managing personal finances often requires manually entering expenses, categorizing transactions, analyzing spending patterns, and planning savings.

**Personal FinAI** combines traditional financial analysis with Generative AI to simplify these tasks through a mobile-oriented Streamlit web application.

The application supports:

- Receipt image scanning using Vision AI
- CSV bank statement analysis
- AI-powered transaction categorization
- Expense analytics and visualization
- SIP and wealth-growth simulation
- AI-powered financial health scoring
- AI-generated spending observations and action plans
- Downloadable financial health reports in PDF format

---

## ✨ Key Features

### 📷 1. AI Receipt Scanner

Users can either:

- Capture a receipt using the device camera
- Upload one or more receipt images

The application uses Vision AI to extract structured information such as:

- Date
- Merchant / description
- Category
- Amount
- Tax amount
- Payment method
- Confidence level
- Summary of purchased items

Multiple receipts can also be processed in parallel.

---

### 📄 2. CSV Bank Statement Analysis

Users can upload a CSV transaction statement.

The application:

1. Reads the transaction data
2. Identifies transaction descriptions
3. Uses Generative AI to categorize transactions
4. Adds categories to the transaction dataset
5. Uses the categorized data for financial analytics

Supported categories include:

- Housing / Rent
- Groceries & Food
- Transportation
- Utilities & Bills
- Shopping
- Entertainment
- Miscellaneous / Other

---

### 📊 3. Financial Analytics

The dashboard calculates and displays:

- Total expenses
- Remaining balance
- Savings target status
- Expense category breakdown
- Income vs. expenses vs. savings target

Interactive charts are generated using Plotly.

---

### 📈 4. SIP & Wealth Simulator

The application provides a basic SIP-based wealth simulation.

Users can configure:

- Monthly SIP amount
- Expected annual return
- Investment duration
- Annual SIP step-up percentage

The application estimates:

- Total amount invested
- Projected wealth
- Year-by-year wealth growth

> The SIP simulator is an educational projection and should not be considered investment advice or a guaranteed return.

---

### 🤖 5. AI Financial Health Audit

The application uses Generative AI to evaluate the user's financial data.

The AI receives information such as:

- Income
- Savings target
- Total expenses
- Category-wise spending
- SIP amount
- Investment duration
- Expected return assumption

It generates:

- Financial health score out of 100
- Financial status
- Executive summary
- Spending observations
- Recommended action plan

---

### 📑 6. PDF Financial Health Report

Users can generate and download a structured PDF report containing:

- Monthly income
- Total spending
- Savings ratio
- Expense-to-income ratio
- Savings target
- Remaining balance
- Expense category breakdown
- Transaction audit ledger
- AI financial health score
- AI-generated diagnostic summary

---

## 🧠 Generative AI Integration

Generative AI is used in multiple parts of the application rather than only as a chatbot.

### AI Use Cases

| Feature | AI Usage |
|---|---|
| Receipt Scanner | Vision AI extracts structured receipt data |
| Transaction Categorization | LLM classifies transaction descriptions |
| Financial Health Audit | LLM analyzes financial information |
| Financial Recommendations | LLM generates observations and action steps |
| Structured Output | JSON responses are used for application processing |

The application uses the **Groq API** to access the configured language and vision models.

---

## 🏗️ Application Workflow

```text
                    ┌─────────────────────┐
                    │       User          │
                    └──────────┬──────────┘
                               │
              ┌────────────────┴────────────────┐
              │                                 │
              ▼                                 ▼
       Receipt Image                       CSV Statement
              │                                 │
              ▼                                 ▼
        Vision AI                         LLM Categorization
              │                                 │
              └──────────────┬──────────────────┘
                             ▼
                  Transaction Information
                             │
                             ▼
                  Financial Data Analysis
                             │
              ┌──────────────┼──────────────┐
              ▼              ▼              ▼
         Analytics      SIP Simulator    AI Health Audit
              │              │              │
              └──────────────┼──────────────┘
                             ▼
                   Financial Health Report
                             │
                             ▼
                       PDF Export
```

---

## 🛠️ Technology Stack

### Application

- **Python**
- **Streamlit**

### Generative AI

- **Groq API**
- LLM-based transaction categorization
- Vision AI-based receipt extraction
- Structured JSON AI responses

### Data Processing

- **Pandas**
- CSV processing
- Transaction aggregation and categorization

### Visualization

- **Plotly**
- Interactive expense and wealth-growth charts

### Image Processing

- **Pillow**
- Receipt image resizing and compression

### Report Generation

- **ReportLab**
- PDF financial health reports

---

## 📱 Application Sections

The application is organized into four main sections:

### 1. 📥 Entry & OCR

- Live camera receipt capture
- Receipt image upload
- Parallel receipt processing
- CSV statement upload
- AI transaction categorization

### 2. 📊 Analytics

- Expense summary
- Net balance
- Savings target status
- Category-wise expense visualization
- Cash-flow comparison

### 3. 📈 Growth

- SIP calculator
- Expected return configuration
- Investment duration
- Annual step-up
- Projected wealth visualization

### 4. 🤖 AI Audit

- Financial health score
- AI-generated summary
- Spending observations
- Action plan
- PDF report generation

---

## 🔐 API Key & Security

The application does **not require an API key to be hard-coded into the source code**.

The Groq API key is entered at runtime through the application's password-type input field and passed to the Groq client when AI functionality is used.

For local development, users should never commit API keys, passwords, or other credentials to the repository.

---

## 🚀 Getting Started

### Prerequisites

- Python 3.x
- A Groq API key
- Git

### 1. Clone the repository

```bash
git clone https://github.com/IoTSec-AI/finai-mobile-app.git
cd finai-mobile-app
```

### 2. Create a virtual environment

#### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

#### Linux / macOS

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the application

```bash
streamlit run app.py
```

### 5. Enter your Groq API key

Open the application in your browser and enter your Groq API key in:

**App Settings → Groq API Key**

---

## 📂 Project Structure

```text
finai-mobile-app/
│
├── .devcontainer/
│
├── app.py
│   └── Main Streamlit application
│
├── requirements.txt
│   └── Python dependencies
│
└── README.md
    └── Project documentation
```

---

## 🎓 SIC Generative AI Capstone

This project was developed as part of the **Samsung Innovation Campus (SIC) Generative AI program**.

The project demonstrates the practical application of Generative AI in a real-world domain by combining:

- Generative AI
- Vision AI
- Python
- Data processing
- Interactive dashboards
- Financial analytics
- Automated reporting

The project focuses on using AI to transform raw financial information into structured insights and actionable recommendations.

---

## 🔮 Future Improvements

Potential future improvements include:

- Persistent user accounts and transaction storage
- Database-backed transaction history
- More robust receipt validation
- Improved financial trend analysis
- Budget alerts and notifications
- Personalized financial goals
- Advanced AI financial insights
- Authentication and authorization
- Secure server-side API key management
- More detailed financial reports
- Deployment with production-grade infrastructure

---

## ⚠️ Disclaimer

Personal FinAI is an educational and demonstration project.

Financial health scores, AI-generated recommendations, SIP projections, and investment calculations are intended for informational purposes only and should **not be considered professional financial, investment, tax, or legal advice**.

Investment returns shown by the simulator are projections based on user-provided assumptions and are not guaranteed.

---

## 👨‍💻 Project

**Personal FinAI — AI-Powered Personal Finance Dashboard**

Developed as part of the **Samsung Innovation Campus Generative AI Capstone Project**.

**Repository:**  
https://github.com/IoTSec-AI/finai-mobile-app
