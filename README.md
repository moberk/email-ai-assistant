# **Email AI Assistant 📧🤖**

## 📋 **Project Overview**  
The **Email AI Assistant** is an automation solution built using **Make.com** that automatically processes incoming emails, classifies the content using **OpenAI's API**, retrieves relevant information from a knowledge base stored in **Google Sheets**, and generates **draft replies in Gmail**. The goal of this project is to efficiently handle customer inquiries by providing quick, automated responses to frequently asked questions.

---

## 🛠️ **Tech Stack & Tools**  
This project integrates several tools and services to achieve seamless email automation:

| Tool/Service     | Purpose                                          |
|------------------|--------------------------------------------------|
| **Make.com**     | No-code platform used to create automation workflows. |
| **Google Sheets** | Stores FAQ questions and answers.               |
| **OpenAI API**   | Processes and classifies incoming emails, and generates human-like responses. |
| **Pinecone**     | Vector database for retrieving relevant FAQ answers. |
| **Gmail API**    | Generates draft responses based on the processed queries. |

---

## ⚙️ **How It Works**  
The solution is divided into **two main workflows** within **Make.com**:

### 1️⃣ **Workflow 1: FAQ Vector Generation (RAG - Retrieval Augmented Generation)**  
This workflow processes the FAQ data from **Google Sheets** and creates **vector embeddings** that are stored in **Pinecone** for quick retrieval.

#### **Steps:**
1. **Google Sheets**: Retrieves the FAQ data (questions and answers).
2. **Tools: Set Variables**: Stores the FAQ data in variables.
3. **OpenAI API**: Converts the text into vector embeddings.
4. **Pinecone**: Uploads the embeddings to the vector database.

---

### 2️⃣ **Workflow 2: Email Processing and Response Generation**  
This workflow monitors **incoming emails in Gmail**, classifies the content using **OpenAI**, retrieves relevant answers from **Pinecone**, and generates a **draft reply in Gmail**.

#### **Steps:**
1. **Gmail**: Watches for new incoming emails.
2. **OpenAI API**: Classifies the email content to determine if it's an FAQ or another type of inquiry.
3. **Router**: Splits the workflow into two routes:
   - **FAQ Route**: Queries Pinecone for a relevant FAQ answer.
   - **Other Route**: Sends a predefined response.
4. **Pinecone**: Retrieves the best match from the FAQ database.
5. **OpenAI API**: Generates a human-like response based on the retrieved information.
6. **Gmail**: Creates a draft email reply.

---

## 🔧 **Configuration Details**  
To set up and run this project, you need to configure the following variables:

| Variable         | Description                                      | Where to Set         |
|------------------|--------------------------------------------------|----------------------|
| `OPENAI_API_KEY` | Your OpenAI API key.                             | Make.com variable    |
| `PINECONE_API_KEY` | Your Pinecone API key.                         | Make.com variable    |
| `GOOGLE_SHEETS_URL` | URL of the Google Sheet containing the FAQ data. | Make.com module      |
| `GMAIL_ACCOUNT`  | The Gmail account used to create draft emails.   | Make.com module      |

---

## 🚀 **How to Run the Project**  
1. **Step 1**: Clone this repository to your local machine or import the provided **Make.com scenario** files into your Make workspace.  
2. **Step 2**: Configure the required variables in **Make.com** (API keys, Google Sheets URL, etc.).  
3. **Step 3**: Connect your **Gmail** account and ensure it has permission to create draft emails.  
4. **Step 4**: Run the scenario and start processing incoming emails automatically.

---

## 🔐 **Security Considerations**  
- **API Keys**: Never hardcode your API keys in the workflow. Use **Make.com variables** to manage sensitive information securely.  
- **Gmail Permissions**: Ensure your Gmail account permissions are correctly configured to avoid issues with draft creation.

---

## 📈 **Future Improvements**  
Some potential improvements to this project include:  
- Adding **error handling** for unstructured emails.  
- Integrating a **UI interface** to manage FAQs.  
- Adding **multi-language support** for email responses.

---

## 🧩 **Dependencies**  
- **OpenAI API**: [https://platform.openai.com/](https://platform.openai.com/)  
- **Pinecone**: [https://www.pinecone.io/](https://www.pinecone.io/)  
- **Google Sheets API**: [https://developers.google.com/sheets/api/](https://developers.google.com/sheets/api/)  
- **Gmail API**: [https://developers.google.com/gmail/api](https://developers.google.com/gmail/api)

---

## 👨‍💻 **Author**  
Developed by **Erick Hernandez**.  
Feel free to reach out for feedback, questions, or collaboration opportunities.

---

## 💬 **Contact**  
📧 **Email**: hernandezme.0626@gmail.com
🔗 **LinkedIn**: [Your LinkedIn Profile](https://www.linkedin.com/in/erick-hdzmtz/)  
