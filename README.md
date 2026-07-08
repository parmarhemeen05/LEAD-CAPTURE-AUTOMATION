# Lead Capture Automation using n8n

## Project Overview

This project automates the lead management process using **n8n**, **Google Sheets**, and **Gmail**. When a new lead is submitted through a webhook (simulating a website contact form), the workflow automatically stores the lead details in Google Sheets, notifies the business owner via email, and sends a confirmation email to the customer.

---

## Objective

- Capture lead information from a form submission.
- Store lead data in Google Sheets.
- Notify the business owner instantly.
- Send an automatic confirmation email to the customer.
- Demonstrate workflow automation using n8n.

---

## Technologies Used

- n8n Cloud
- Google Sheets API
- Gmail API
- Postman
- Google Sheets
- VS Code

---

## Workflow

```
Webhook
    │
    ▼
Google Sheets (Append Row)
    │
    ▼
Gmail (Business Owner Notification)
    │
    ▼
Gmail (Customer Auto Reply)
```

---

## Workflow Description

### 1. Webhook Trigger
- Receives lead details via HTTP POST request.
- Input fields:
  - Name
  - Phone
  - Email
  - Requirement

### 2. Google Sheets
- Appends every lead into a Google Sheet named **Lead CRM**.
- Stores:
  - Name
  - Phone
  - Email
  - Requirement
  - Date & Time

### 3. Business Owner Notification
- Sends an email to the business owner whenever a new lead is received.
- Includes complete lead information.

### 4. Customer Auto Reply
- Sends a confirmation email to the customer.
- Confirms that the inquiry has been received successfully.

---

## Sample Input (Webhook)

```json
{
  "name": "Hemeen Parmar",
  "phone": "9876543210",
  "email": "parmarhemeen05@gmail.com",
  "requirement": "Need a Website"
}
```

---

## Output

### Google Sheets

| Name | Phone | Email | Requirement | Date |
|------|-------|-------|-------------|------|
| Hemeen Parmar | 9876543210 | hemeen@example.com | Need a Website | Auto Generated |

---

### Business Owner Email

**Subject**

```
New Lead Received
```

**Body**

```
New Lead Received!

Name: Hemeen Parmar
Phone: 9876543210
Email: hemeen@example.com
Requirement: Need a Website
```

---

### Customer Email

**Subject**

```
Thank You for Contacting Us
```

**Body**

```
Hello Hemeen Parmar,

Thank you for contacting us.

We have received your inquiry regarding:
Need a Website

Our team will review your request and contact you shortly.

Regards,
Hemeen Parmar
```

---

## Project Structure

```
Lead-Capture-Automation/
│
├── workflow.json
├── README.md
├── report.pdf
├── Lead-Capture.postman_collection.json
│
└── screenshots/
    ├── workflow.png
    ├── webhook.png
    ├── postman.png
    ├── sheets.png
    ├── owner-email.png
    ├── customer-email.png
```

---

## How to Run the Project

1. Open the workflow in n8n.
2. Activate the workflow.
3. Copy the Production Webhook URL.
4. Open Postman.
5. Send a POST request with JSON data.
6. Verify that:
   - A new row is added to Google Sheets.
   - The business owner receives an email.
   - The customer receives a confirmation email.

---

## Features

- Automated lead capture
- Google Sheets integration
- Email notifications
- Customer auto-response
- No manual data entry
- Cloud-based workflow automation

---

## Future Improvements

- WhatsApp notifications using Twilio or WAHA
- CRM integration
- Duplicate lead detection
- Lead status tracking
- Dashboard and analytics
- File attachment support

---

## Author

**Hemeen Parmar**

Computer Science & Engineering Student

R.N.G.P.I.T.

GitHub: https://github.com/parmarhemeen05

---

## License

This project is developed for educational and internship assignment purposes.
