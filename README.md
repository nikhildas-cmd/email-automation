# 🤖 Human-in-the-Loop AI Email Automation (n8n + IMAP + OpenAI)

This workflow automates the handling of **incoming emails**, generates **AI-powered responses**, and keeps a **human in the loop** for approval before sending.

---

## 🚀 How It Works

1. **Email Trigger (IMAP)**  
   - Reads incoming emails from your inbox (Gmail/Outlook/Custom IMAP).  

2. **Markdown Conversion**  
   - Converts HTML emails into clean Markdown for better LLM processing.  

3. **Email Summarization Chain**  
   - Summarizes the email into ≤100 words using LLMs (OpenAI / DeepSeek).  
   - Ensures faster human understanding.  

4. **AI Agent – Draft Reply**  
   - Generates a **professional, business-style email response**.  
   - Concise (≤100 words) and context-aware.  

5. **Human-in-the-Loop (Approval)**  
   - The draft response is sent to your inbox for review.  
   - You approve or reject with one click.  

6. **Send Final Email**  
   - If approved, the system automatically replies to the sender.  

---

## 🔧 Tech Stack

- **n8n** → Workflow automation  
- **IMAP** → Email fetching  
- **SMTP** → Email sending  
- **LangChain** → Summarization + Agent logic  
- **OpenAI / DeepSeek** → AI language models  

---

## 📂 Workflow Overview

```mermaid
flowchart TD
    A[Incoming Email via IMAP] --> B[Convert to Markdown]
    B --> C[Summarize Email with LLM]
    C --> D[Generate AI Reply]
    D --> E[Send for Human Approval]
    E -->|Approved| F[Send Final Email via SMTP]
    E -->|Rejected| G[Stop or Modify]
