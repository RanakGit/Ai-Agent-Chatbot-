# AI Agent Chatbot – RAC Insurance README

## Project Overview

This project is an AI-powered customer support chatbot built using [n8n](https://n8n.io?utm_source=chatgpt.com), [Google Gemini AI](https://ai.google.dev?utm_source=chatgpt.com), [Google Sheets](https://www.google.com/sheets/about/?utm_source=chatgpt.com), and [Gmail](https://mail.google.com?utm_source=chatgpt.com).

The chatbot is designed for **RAC Insurance** to provide intelligent automated support to customers by:

* Answering customer queries
* Accessing company/product information from Google Sheets
* Maintaining conversation memory
* Sending emails to company officials when needed
* Providing a live AI chat experience

---

# Workflow Name

**AI Agent Chatbot – RAC Insurance**

---

# Features

* AI-powered customer support chatbot
* Real-time conversational interface
* Google Gemini AI integration
* Google Sheets knowledge base
* Conversational memory support
* Automated Gmail functionality
* Public chat interface
* Context-aware responses

---

# Workflow Architecture

```text id="4x31sv"
User Message
      │
      ▼
Chat Trigger
      │
      ▼
AI Agent
 ┌───────────────┬────────────────┬────────────────┐
 ▼               ▼                ▼
Gemini AI    Google Sheets     Memory Buffer
 Model          Tool
      │
      ▼
Generate Intelligent Response
      │
      └────► Gmail Tool (Optional)
```

---

# Nodes Used

## 1. Chat Trigger Node

### Purpose

Starts the chatbot whenever a user sends a message.

### Features

* Publicly accessible chatbot
* Custom welcome message
* Real-time interaction

### Initial Message

```text id="r2k4t1"
Hi there! 👋 How can I assist you today?
```

---

## 2. AI Agent Node

### Purpose

Acts as the central intelligence controller of the chatbot.

### Responsibilities

* Understands customer queries
* Uses tools dynamically
* Retrieves company information
* Maintains conversational flow
* Decides when to send emails

### System Prompt

The AI agent is instructed to:

* Help RAC Insurance customers
* Check Google Sheets before answering
* Use Gmail for official communication

---

## 3. Google Gemini Chat Model

### Purpose

Provides advanced Large Language Model (LLM) capabilities.

### Model Used

Google Gemini AI

### Capabilities

* Natural language understanding
* Contextual conversation
* Intelligent response generation
* Query interpretation

---

## 4. Google Sheets Tool

### Purpose

Acts as the knowledge base for RAC Insurance.

### Description

The sheet contains:

* Company details
* Insurance products
* Service information
* Customer support data

### Spreadsheet Used

`RAC Company Details`

### Functionality

* Retrieves rows dynamically
* Allows AI to answer accurately
* Provides structured business information

---

## 5. Simple Memory Node

### Purpose

Maintains short-term conversation memory.

### Configuration

```text id="z9wl3m"
Context Window Length: 10
```

### Benefits

* Remembers previous messages
* Enables context-aware replies
* Improves user experience

---

## 6. Gmail Tool Node

### Purpose

Allows the AI agent to send emails directly to company officials.

### Features

* AI-generated subject line
* AI-generated message body
* CC support enabled

### Email Usage Examples

* Escalating customer issues
* Sending support requests
* Reporting important incidents
* Forwarding user concerns

---

# Technologies Used

| Technology                                                                           | Purpose             |
| ------------------------------------------------------------------------------------ | ------------------- |
| [n8n](https://n8n.io?utm_source=chatgpt.com)                                         | Workflow Automation |
| [Google Gemini AI](https://ai.google.dev?utm_source=chatgpt.com)                     | AI Language Model   |
| [Google Sheets API](https://developers.google.com/sheets/api?utm_source=chatgpt.com) | Knowledge Base      |
| [Gmail API](https://developers.google.com/gmail/api?utm_source=chatgpt.com)          | Email Automation    |

---

# Workflow Connections

## Main Workflow Flow

```text id="1fyjlwm"
Chat Trigger
     ↓
AI Agent
     ↓
Gemini Model + Memory + Google Sheets + Gmail Tool
```

---

# Setup Instructions

## Step 1 — Import Workflow

1. Open n8n
2. Navigate to **Workflows**
3. Click **Import from JSON**
4. Paste the workflow JSON
5. Save the workflow

---

## Step 2 — Configure Credentials

Connect the following credentials:

* Google Gemini API
* Google Sheets OAuth2
* Gmail OAuth2

---

## Step 3 — Prepare Google Sheet

Create a Google Sheet containing:

```text id="vq7r5x"
- Insurance Product Details
- Company Policies
- Support Information
- FAQs
- Contact Information
```

---

## Step 4 — Activate Workflow

Enable the workflow by switching:

```text id="u0c9ld"
Inactive → Active
```

---

# Example User Interaction

## User Query

```text id="91w4t2"
What insurance plans does RAC Insurance provide?
```

## AI Agent Process

1. Receives user message
2. Checks Google Sheets data
3. Uses Gemini AI to generate response
4. Replies intelligently to customer

---

# Example Escalation Workflow

## User Message

```text id="m1n0rz"
I want to report a major issue with my policy.
```

## AI Agent Action

* Understands urgency
* Generates professional email
* Sends email to company officials automatically

---

# Benefits

* 24/7 customer support
* Reduced manual workload
* Faster query resolution
* Centralized company knowledge
* Intelligent AI-driven interaction
* Automated escalation system
* Better customer experience

---

# Future Improvements

Possible future upgrades:

* Voice-enabled chatbot
* WhatsApp integration
* CRM integration
* Database memory storage
* Multi-language support
* Sentiment analysis
* Live agent handoff
* Ticket management system

---

# Security Considerations

* OAuth2 authentication used
* Controlled Gmail access
* Secure Google Sheets integration
* AI operates within configured permissions

---

# Author

**Ranak Halder**
B.Tech Biotechnology Student & AI Automation Enthusiast

---

# License

This project is open for educational, demonstration, and internal business automation purposes.
