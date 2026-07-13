# 🤖 AI Address Validator using n8n

> An AI-powered workflow built with **n8n**, **Google Sheets**, **LLM (Mistral AI)**, and **Telegram** to automatically validate customer addresses at scale.

---

## 📌 Overview

Businesses receive thousands of customer addresses every day through e-commerce websites, delivery platforms, CRMs, and order management systems.

Manually checking whether an address is complete, valid, or too short is:

- Time-consuming
- Error-prone
- Expensive
- Difficult to scale

This project automates the entire validation process using AI.

The workflow reads customer records from Google Sheets, sends each address to an LLM for validation, writes the validation result back into the sheet, and finally notifies the user on Telegram when processing is complete.

---

# 🚀 Real World Problem

Many companies face issues like:

- Incomplete delivery addresses
- Missing locality or street names
- Very short addresses
- Invalid shipping information
- Manual verification by customer support teams

These problems often result in:

- Failed deliveries
- Increased logistics cost
- Customer dissatisfaction
- Delayed order processing

Manual validation becomes impossible when processing hundreds or thousands of orders daily.

---

# 💡 Solution

This workflow completely automates address validation.

Instead of manually checking every address, AI analyzes each record and classifies it.

Example outputs:

✅ VALID

⚠️ Too Short

❌ Invalid Address

The validated result is automatically written back into Google Sheets.

After completion, a Telegram notification is sent.

---

# 🏗 Workflow Architecture

```
Telegram Trigger
        │
        ▼
Google Sheets
(Read Customer Records)
        │
        ▼
Filter Empty Remarks
        │
        ▼
Mistral AI (LLM)
Address Validation
        │
        ▼
Process AI Response
        │
        ▼
Merge Results
        │
        ▼
Update Google Sheet
        │
        ▼
Telegram Notification
```

---

# ⚙️ Technologies Used

- n8n
- Mistral AI
- Google Sheets API
- Telegram Bot API
- Large Language Models (LLM)

---

# 📂 Input Data

The workflow reads customer data from Google Sheets.

Example:

| Order ID | Customer | Address | City | Pincode |
|----------|----------|----------|------|----------|
| ORD202600001 | Rahul Shah | 15 MG Road | Surat | 395007 |
| ORD202600002 | Priya Patel | Block A | Ahmedabad | 380001 |

Initially the **Remark** column is empty.

---

# 🤖 AI Validation

The LLM evaluates each address based on:

- Address completeness
- Meaningful street information
- Address length
- Presence of location details
- Overall usability for delivery

Example:

Input

```
15 MG Road
```

Output

```
Too Short
```

---

Input

```
622 Sector 5 Station Road Delhi
```

Output

```
VALID
```

---

# ✅ Output

After validation, Google Sheet becomes:

| Remark | Order ID | Customer |
|---------|----------|----------|
| VALID | ORD202600185 | Akshit Shah |
| Too Short | ORD202600188 | Vivaan Mishra |
| VALID | ORD202600190 | Priya Mishra |

---

# 📲 Telegram Notification

Once every record is processed, the workflow automatically sends a confirmation message.

Example:

```
Done ✅

Please check the Google Sheet.

Address validation completed successfully.
```

---

# 🔄 Workflow Steps

1. User starts workflow from Telegram.
2. n8n reads all customer records.
3. Records with empty remarks are selected.
4. Each address is sent to Mistral AI.
5. AI validates the address.
6. Validation result is formatted.
7. Google Sheet is updated.
8. Telegram notification is sent.

---

# 📈 Features

- Fully automated
- No manual validation
- AI-powered decision making
- Google Sheets integration
- Telegram integration
- Batch processing
- Scalable workflow
- Easy to customize

---

# 📊 Business Benefits

- Reduce manual work
- Faster order verification
- Lower operational cost
- Improve delivery success rate
- Better customer satisfaction
- Easily scalable to thousands of records

---

# 📸 Project Screenshots

## n8n Workflow

(Add Screenshot)

---

## Google Sheet Before Validation

(Add Screenshot)

---

## Google Sheet After Validation

(Add Screenshot)

---

## Telegram Notification

(Add Screenshot)

---

# 📁 Project Structure

```
AI-Address-Validator/
│
├── workflow.json
├── README.md
├── images/
│     ├── 1.png
│     ├── 2.png
│     ├── 3.png
│     └── 4.png
│
└── sample_data.xlsx
```

---

# 🔮 Future Improvements

- Address standardization
- Google Maps API verification
- Postal code validation
- Duplicate address detection
- Confidence score
- Multi-language support
- CRM integration
- Email notifications
- Dashboard using Power BI

---

# 👨‍💻 Author

**Akshit Gajera**

AI Engineer | Data Scientist | AI Automation Developer

GitHub:
https://github.com/akshitgajera1013

---

# ⭐ If you found this project useful, don't forget to give it a Star!