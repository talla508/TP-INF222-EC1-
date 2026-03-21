# Blog API - TAF INF222 EC1

RESTful Backend API for managing a simple blog with full CRUD operations on articles.

## Technologies

- **Node.js** + **Express** - Web server
- **SQLite** (sql.js) - Database
- **Swagger UI** - API documentation
- **express-validator** - Input validation

## Installation

```bash
# Clone the repository
git clone https://github.com/talla508/blog-api.git
cd blog-api

# Install dependencies
npm install

# Start in development mode (auto-restart)
npm run dev

# Start in production mode
npm start```

Server starts on http://localhost:3000

API Documentation
Access Swagger UI: http://localhost:3000/api-docs

## Endpoints

Method	Endpoint	Description
POST	/api/articles	Create a new article
GET	/api/articles	Get all articles
GET	/api/articles/:id	Get article by ID
PUT	/api/articles/:id	Update an article
DELETE	/api/articles/:id	Delete an article
GET	/api/articles/search?query=text	Search articles
Available Filters (GET /api/articles)
?categorie=Technology
?auteur=Charles
?date=21/03/2026
Date Format
All dates use DD/MM/YYYY format.

Usage Examples
Create an article
Bash

curl -X POST http://localhost:3000/api/articles \
  -H "Content-Type: application/json" \
  -d '{
    "titre": "Introduction to Web Development",
    "contenu": "Web development is a fascinating field that keeps evolving...",
    "auteur": "Charles",
    "date": "21/03/2026",
    "categorie": "Technology",
    "tags": ["web", "backend", "nodejs"]
  }'
Get all articles
Bash

curl http://localhost:3000/api/articles
Get article by ID
Bash

curl http://localhost:3000/api/articles/1
Update an article
Bash

curl -X PUT http://localhost:3000/api/articles/1 \
  -H "Content-Type: application/json" \
  -d '{
    "titre": "Updated Title",
    "contenu": "Updated content...",
    "auteur": "Charles",
    "date": "21/03/2026",
    "categorie": "Technology",
    "tags": ["web", "updated"]
  }'
Delete an article
Bash

curl -X DELETE http://localhost:3000/api/articles/1
Search articles
Bash

curl "http://localhost:3000/api/articles/search?query=web"
Filter articles
Bash

curl "http://localhost:3000/api/articles?categorie=Technology"
curl "http://localhost:3000/api/articles?auteur=Charles"
curl "http://localhost:3000/api/articles?date=21/03/2026"
Project Structure
text

blog-api/
├── config/
│   └── database.js            # SQLite database configuration
├── controllers/
│   └── articleController.js   # Request handling logic
├── middlewares/
│   └── validation.js          # Input validation rules
├── models/
│   └── articleModel.js        # Database operations
├── routes/
│   └── articleRoutes.js       # API route definitions
├── app.js                     # Express app setup
├── server.js                  # Server entry point
├── swagger.js                 # Swagger documentation
├── package.json
├── blog.db                    # SQLite database file
└── README.md
HTTP Status Codes
Code	Meaning
200	OK - Success
201	Created - Article created
400	Bad Request - Invalid input
404	Not Found - Article not found
500	Internal Server Error
Best Practices
Input validation (title not empty, author required...)
Correct HTTP status codes
MVC architecture (Routes, Controllers, Models)
Error handling with descriptive messages
Date format DD/MM/YYYY
API documentation with Swagger
Author
NZOKOU TALLA DUVAL
