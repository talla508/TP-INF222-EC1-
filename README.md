# Blog API - TAF INF222 EC1

RESTful Backend API for managing a simple blog with full CRUD operations on articles.

## Technologies

- **Node.js** + **Express** - Web server
- **SQLite** (sql.js) - Database
- **Swagger UI** - API documentation
- **express-validator** - Input validation

## Installation

```bash
git clone https://github.com/talla508/blog-api.git
cd blog-api
npm install
npm run dev
```
**Server starts on http**://localhost:3000

**Swagger UI**: http://localhost:3000/api-docs

**Endpoints**
Method	Endpoint	Description
POST	/api/articles	Create an article
GET	/api/articles	Get all articles
GET	/api/articles/:id	Get article by ID
PUT	/api/articles/:id	Update an article
DELETE	/api/articles/:id	Delete an article
GET	/api/articles/search?query=text	Search articles
Filters
categorie=Technology
auteur=Charles
date=21/03/2026
Date Format
All dates use DD/MM/YYYY format.

Project Structure
text

blog-api/
├── config/database.js
├── controllers/articleController.js
├── middlewares/validation.js
├── models/articleModel.js
├── routes/articleRoutes.js
├── app.js
├── server.js
├── swagger.js
├── blog.db
└── README.md
**HTTP Status Codes**
Code	Meaning
200	  OK
201	  Created
400 	Bad Request
404	  Not Found
500 	Internal Server Error
**Author**
NZOKOU TALLA DUVAL
