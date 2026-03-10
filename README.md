# AI Resume Generator using n8n, LLM, and Telegram

## Overview

This project is an **AI-powered automated resume generation system** built using **n8n workflow automation, Groq LLM, and Telegram Bot integration**.

The system allows a user to send a **Job Description (JD)** through Telegram. The workflow automatically processes the JD, combines it with a pre-stored base resume, generates a **customized ATS-optimized resume**, converts it into **PDF format**, and sends the final resume back to the user through Telegram.

The goal of this project is to demonstrate **LLM orchestration, workflow automation, and real-world AI application development**.

---

# Architecture

User → Telegram Bot → n8n Workflow → LLM (Groq) → HTML Resume → PDF Generation → Telegram Response

---

# Workflow Overview

The automation pipeline performs the following steps:

1. **Telegram Trigger**

   * User sends a job description to the Telegram bot.

2. **Extract Job Description**

   * n8n extracts the JD text and user chat ID.

3. **Load Base Resume**

   * The system loads the candidate's base resume stored as a PDF.

4. **Extract Resume Text**

   * The resume content is converted from PDF to text.

5. **Prompt Builder**

   * A structured prompt is created containing:
   * Job Description
   * Base Resume
   * Resume generation instructions

6. **LLM Resume Generation**

   * The prompt is sent to Groq LLM.
   * The model generates an **ATS-optimized resume in HTML format**.

7. **HTML Cleaning**

   * The response is cleaned to remove markdown formatting.

8. **HTML → PDF Conversion**

   * HTML resume is sent to a PDF generation API.

9. **Download Generated PDF**

   * The PDF file is downloaded from the returned API URL.

10. **Send Resume to Telegram**

    * The final PDF resume is sent back to the user in the Telegram chat.

---

# System Architecture Diagram

Telegram User
↓
Telegram Bot Trigger (n8n)
↓
Extract Job Description
↓
Load Base Resume
↓
Extract Resume Text
↓
Prompt Builder
↓
Groq LLM (Resume Generation)
↓
Extract HTML
↓
HTML → PDF Conversion
↓
Download PDF
↓
Send Resume via Telegram

---

# Technologies Used

| Technology         | Purpose                             |
| ------------------ | ----------------------------------- |
| n8n                | Workflow automation engine          |
| Telegram Bot       | User interface                      |
| Groq LLM           | Resume generation                   |
| HTML               | Resume formatting                   |
| PDF Generation API | Convert HTML resume to PDF          |
| GitHub             | Version control and project hosting |

---

# Key Features

• Automatic resume generation from job descriptions
• ATS-optimized resume structure
• Fully automated workflow
• LLM-powered resume rewriting
• PDF resume delivery via Telegram
• No manual editing required

---

# Example Workflow

User sends a message:

Looking for Data Engineer with experience in Python, Spark, Kafka, and Airflow.

The system automatically returns:

resume.pdf

A tailored resume optimized for the provided job description.

---

# Installation & Setup

## 1. Install n8n

You can install n8n using:

npm install n8n -g

or run via Docker.

---

## 2. Import Workflow

1. Open the n8n editor
2. Click **Import Workflow**
3. Upload the workflow JSON file located in:

/workflows/resume-generator-workflow.json

---

## 3. Configure Credentials

Add credentials for:

• Telegram Bot API
• Groq API key
• PDF generation API

---

## 4. Start the Workflow

Once configured:

1. Activate the workflow
2. Send a job description to your Telegram bot
3. Receive a generated resume automatically

---

# Project Structure

ai-resume-generator-n8n
│
├── workflows
│   └── resume-generator-workflow.json
│
├── docs
│   └── architecture.png
│
└── README.md

---

# Example Use Cases

• Job seekers generating tailored resumes quickly
• AI resume assistant tools
• Automated job application systems
• AI-powered recruitment platforms

---

# Future Improvements

• ATS score evaluation
• Multiple resume templates
• Cover letter generation
• JD skill extraction agent
• Resume keyword optimization
• Job matching system

---

# Author

Aditya Sharma

AI & Data Science Graduate
Specializing in AI workflows, automation, and data engineering.

---

# License

This project is for educational and demonstration purposes.
