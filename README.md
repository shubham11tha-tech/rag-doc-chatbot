# RAG Document Chatbot

A full-stack **Retrieval-Augmented Generation (RAG)** chatbot that allows users to upload documents and ask context-aware questions based on their content.

The application retrieves relevant information from uploaded documents and uses AI to generate accurate, document-grounded answers.

## Features

* User registration and login with JWT authentication
* Upload documents for AI-powered question answering
* Ask questions based on uploaded document content
* Context-aware responses using RAG
* View uploaded documents
* Delete uploaded documents
* Responsive React frontend
* Django REST API backend
* Vector database support using ChromaDB
* Google Gemini integration for answer generation

## Tech Stack

### Frontend

* React.js
* Vite
* Axios
* CSS

### Backend

* Python
* Django
* Django REST Framework
* JWT Authentication
* LangChain
* ChromaDB
* Google Gemini API
* Hugging Face embeddings

## Project Structure

```text
RAG-main/
│
├── frontend/
│   └── chat_ui/
│       ├── src/
│       │   ├── auth/
│       │   ├── components/
│       │   ├── pages/
│       │   ├── App.jsx
│       │   └── main.jsx
│       ├── package.json
│       └── vite.config.js
│
├── rag_chatbot/
│   ├── chatbot/
│   │   ├── models.py
│   │   ├── views.py
│   │   ├── urls.py
│   │   └── migrations/
│   ├── rag_chatbot/
│   │   ├── settings.py
│   │   └── urls.py
│   ├── manage.py
│   └── requirements.txt
│
└── README.md
```

## How It Works

1. A user creates an account or logs in.
2. The user uploads one or more documents.
3. The backend extracts and processes document text.
4. Text is split into chunks and stored in ChromaDB as vector embeddings.
5. When the user asks a question, the system retrieves the most relevant document chunks.
6. Google Gemini generates an answer using the retrieved context.
7. The answer is shown in the chatbot interface.

## Installation and Setup

### Prerequisites

Make sure you have installed:

* Python 3.10 or higher
* Node.js and npm
* Git
* A Google Gemini API key

## 1. Clone the Repository

```bash
git clone https://github.com/shubham11tha-tech/rag-doc-chatbot.git
cd rag-doc-chatbot
```

## 2. Backend Setup

Open a terminal and run:

```bash
cd rag_chatbot
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

Create a `.env` file inside the `rag_chatbot` folder and add your API keys:

```env
DJANGO_SECRET_KEY=your_django_secret_key
GEMINI_API_KEY=your_google_gemini_api_key
```

Run database migrations:

```bash
python manage.py migrate
```

Start the Django backend:

```bash
python manage.py runserver
```

The backend will run at:

```text
http://127.0.0.1:8000
```

## 3. Frontend Setup

Open another terminal and run:

```bash
cd frontend/chat_ui
npm install
npm run dev
```

The frontend will run at:

```text
http://localhost:5173
```

## API Endpoints

| Method | Endpoint                               | Description                            |
| ------ | -------------------------------------- | -------------------------------------- |
| POST   | `/api/auth/register/`                  | Create a new user account              |
| POST   | `/api/auth/token/`                     | Login and get JWT tokens               |
| POST   | `/api/auth/token/refresh/`             | Refresh access token                   |
| GET    | `/api/auth/me/`                        | Get current user details               |
| POST   | `/api/documents/upload/`               | Upload documents                       |
| GET    | `/api/documents/`                      | Get uploaded documents                 |
| DELETE | `/api/documents/{document_id}/delete/` | Delete a document                      |
| POST   | `/api/query/`                          | Ask a question from uploaded documents |

## Example Questions

After uploading a document, try questions like:

* `Give me a short summary of this document.`
* `What are the main topics in this PDF?`
* `Explain this topic in easy language.`
* `Give me 5 important points from this document.`
* `Create 10 MCQs with answers from this document.`
* `What is the conclusion of this document?`
* `Make important exam questions from this PDF.`

## Environment Variables

Do not upload your `.env` file to GitHub.

Example:

```env
DJANGO_SECRET_KEY=your_secret_key_here
GEMINI_API_KEY=your_gemini_api_key_here
```

## Screenshots

Add your project screenshots here.

```md
![Login Page](Images_demo/login.png)
![Document Upload](Images_demo/DocUpload.png)
![Chat Interface](Images_demo/ChatInterface.png)
```

## Future Improvements

* Support more document formats
* Add chat history persistence
* Add document preview
* Improve source citations in answers
* Add role-based user access
* Deploy frontend and backend permanently
* Add streaming AI responses
* Add dark mode

## Author

**Shubham Singh AND Bhavya Sherwal**

GitHub: https://github.com/shubham11tha-tech
 GitHub:https://github.com/bhavyasherwal

## License

This project is created for learning and portfolio purposes.
