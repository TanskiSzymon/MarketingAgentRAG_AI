Marketing Automation Workflow (n8n)

This project is a complete n8n workflow designed for automating LoRA model training, product photo generation, and order management using Google Sheets, Drive, Gmail, Replicate, and Qdrant.

---

##  Results Preview

![example1](https://github.com/user-attachments/assets/e02e6712-bd02-45d7-ae4e-aaf42bc667d6)

![example2](https://github.com/user-attachments/assets/bb4f4dbf-8cdc-4ef2-b340-61685e940b59)

![image](https://github.com/user-attachments/assets/be86cab5-6981-49e2-8152-ba60f60ff86b)

*More results in Example1_output_image and Example2_output_image
---

## Demo Video

<p align="center">
  <a href="https://www.youtube.com/watch?v=lyQkkeuPuW0">
     <img src="https://img.youtube.com/vi/lyQkkeuPuW0/0.jpg" alt="Watch the video.">
  </a>
</p>

---

## Project Details


![Diagram](https://github.com/user-attachments/assets/d1d07422-4908-48a0-9065-10872431918a)

- **Technology:** n8n
- **Integrations:**
  - Google Sheets
  - Google Drive
  - Gmail
  - Replicate API
  - Qdrant (vector database)
  - OpenAI (Embeddings, LLM)

- **Main Features:**
  - Automatic LoRA model training based on user-uploaded images
  - Google Drive photo management
  - Google Sheets order tracking and data management
  - Automatic product content retrieval from PDF (using RAG)
  - Generation of creative, highly customized image prompts
  - Complete automation of the workflow without manual coding

- **Data Source:**
  - The main source of truth is the `Orders` Google Sheet.
  - Each record includes:
    - Order number
    - Payment status
    - Training status
    - Number of generated images
    - Model version info
  - (Note: In production, it is highly recommended to migrate to a real database instead of Google Sheets for better scalability.)

- **Inputs Required:**
  - **10–20 high-quality photos** of the product/object from different angles and with good lighting.
  - **One detailed PDF file** describing the product (use, material, style, color, technical details).
  - Detailed product descriptions significantly improve the quality of generated graphics because the AI agent uses this data to create realistic and striking prompts.

- **Important Notes:**
  - The project uses RAG (Retrieval-Augmented Generation) to analyze the PDF file and extract important content.
  - If the input data is very small, RAG can easily be disabled for faster execution.
  - You are **not limited** to training perfume bottles or cosmetics — **any object** can be trained (e.g., shoes, furniture, tech gadgets).
  - Once the model is trained, it appears in your Replicate account under "Models," and remains accessible for future generations without retraining.

- **Performance and Costs:**
  - **Training cost:** ~1 USD per model (based on Replicate pricing and number of photos).
  - **Image generation cost:** typically **below 0.01 USD** per image.
  - The workflow is optimized to minimize token usage and API costs.

- **Current Status:**
  - This is an **early (draft) version**.
  - Many improvements and upgrades are planned, including:
    - Better image quality and faster generation
    - Workflow modularization
    - Automated video generation from photos
  - Even in its current form, the system delivers **satisfying and production-ready results**.

---

## Setup Instructions

1. Install and configure n8n.
2. Create necessary Credentials (Google, Replicate, OpenAI, Qdrant).
3. Import the workflow into your instance.
4. Insert your API keys and configure endpoint details.
5. Provide proper photos and PDF documents for each order.
6. Run the workflow and enjoy automated generation!

---

## Requirements

- Google Cloud account (for OAuth 2.0)
- Replicate account
- OpenAI account
- Qdrant Cloud account (or private instance)

