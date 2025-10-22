# 🧩 Core API Layer Project

This repository serves as the **foundational layer** for a modern, scalable **Node.js REST API**.  
It provides a professional project structure, standardized response contracts, and integrated API documentation out-of-the-box — offering a **robust starting point** for any new service.

---

## 🚀 Features

- **Structured & Scalable:** Logical separation of concerns for API logic, middleware, and configuration.  
- **Versioned API:** All endpoints are nested under `/api/v1` to support future versions without breaking changes.  
- **Standardized Responses:** Consistent JSON structure for all success and error responses.  
- **Integrated Documentation:** Live, interactive API docs powered by **OpenAPI** and **Swagger UI**.  
- **Centralized Error Handling:** Graceful error management that prevents internal stack traces from leaking.

---

## ⚙️ Getting Started

Follow these instructions to set up and run the project locally.

### 📋 Prerequisites

- [Node.js (LTS)](https://nodejs.org/)
- npm (comes preinstalled with Node.js)

---

### 🧑‍💻 Installation & Setup

1. **Clone the repository**
   ```bash
   git clone <your-repository-url>
   cd core-api-layer
Install dependencies

bash
Copy code
npm install
Configure environment variables

Create a .env file in the root directory:

bash
Copy code
PORT=3000
NODE_ENV=development
⚠️ .env is ignored by Git and should never contain sensitive data in public repos.

Start the server

bash
Copy code
npm start
If npm start doesn’t exist, add this line to your package.json:

json
Copy code
"scripts": {
  "start": "node src/server.js"
}
You should then see:

nginx
Copy code
API listening on http://localhost:3000
🗂️ Project Structure
bash
Copy code
/
├── docs/
│   └── OpenAPI.yaml          # API specification file
├── src/
│   ├── api/
│   │   └── v1/
│   │       ├── index.js              # V1 main router
│   │       ├── ping.routes.js        # Routes for /ping
│   │       └── system.routes.js      # Routes for healthcheck/status
│   ├── middleware/
│   │   ├── error-handler.js          # Global error handler
│   │   └── response-shape.js         # Standardized response middleware
│   ├── app.js                        # Express app setup
│   └── server.js                     # Server entry point
├── .env                              # Environment variables (local only)
├── .gitignore                        # Git ignored files
├── package.json                      # Dependencies & scripts
└── README.md                         # You are here!
📖 API Documentation
This API is documented using OpenAPI 3.0 and visualized with Swagger UI.

Access the Docs
Start the server (npm start)

Visit http://localhost:3000/api/docs

You can explore and test endpoints directly using the “Try it out” button.

📬 API Response Contract
All responses follow a consistent JSON format for predictability and ease of integration.

✅ Success Response
Shape:

json
Copy code
{
  "success": true,
  "data": { ... }
}
HTTP Status: 200 OK

Example:

json
Copy code
{
  "success": true,
  "data": {
    "version": "v1",
    "ok": true
  }
}
❌ Error Response
Shape:

json
Copy code
{
  "success": false,
  "error": {
    "message": "...",
    "code": "..."
  }
}
HTTP Status: 4xx or 5xx

Example (404 Not Found):

json
Copy code
{
  "success": false,
  "error": {
    "message": "API route not found.",
    "code": "NOT_FOUND"
  }
}
👥 Contributing
Fork the repository

Create your feature branch (git checkout -b feature/your-feature)

Commit your changes (git commit -m 'Add new feature')

Push to the branch (git push origin feature/your-feature)

Create a Pull Request