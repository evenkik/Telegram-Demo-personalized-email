# n8n Demo workflow for AI & Automation Agencies

This n8n workflow is built for AI and automation agencies to **promote their workflows through an interactive demo** that prospects can try themselves.  
The featured system is a **deep personalized email demo**.

---

## 🚀 Features

- **Telegram interface** using the BotFather API  
- **Instructor and RAG agent** to guide prospects through the demo  
- **Flow generation limits per user ID** to prevent abuse  
- **Low-cost yet powerful web scraping**, escalating from low- to high-CPU flows if earlier ones fail  

---

## 💡 Development Ideas

- Replace the RAG logic with your own query-answering and guidance method  
- Remove the flow limit if you’re confident the demo can’t be misused  
- Swap the personalized email demo with any other workflow you want to showcase  

---

## 🧠 Technical Notes

- **Telegram bot** created with BotFather  
- **Website crawl process:**
  - Extract sub-links via `/sitemap.xml`, `sitemap_index.xml`, or standard HTTP requests  
  - Fall back to **Crawl4AI** if normal requests fail  
  - Fetch sub-link content via HTTPS or Crawl4AI as backup  
- **SparkPost** used for sending demo emails  

---

## ⚙️ Setup Instructions

### 1. Create a Telegram Bot
- Use **BotFather** on Telegram to create your bot and get the **API token**.  
- This token will be used to connect your n8n workflow to Telegram.  

### 2. Create a Log Data Table
- In your database, create a table to store user logs.  
- The table must include at least the following columns:
  - `name` — to store the user’s name or Telegram username.  
  - `id` — to store the user’s unique identifier.  

### 3. Install Crawl4AI with Docker
- Follow the installation guide from the official repository:  
  👉 [https://github.com/unclecode/crawl4ai](https://github.com/unclecode/crawl4ai)  
- **Crawl4AI** will handle website crawling and content extraction in your workflow.  

---
