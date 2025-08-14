[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=20084909&assignment_repo_type=AssignmentRepo)
# Express.js RESTful API Assignment

This assignment focuses on building a RESTful API using Express.js, implementing proper routing, middleware, and error handling.

## Assignment Overview

You will:
1. Set up an Express.js server
2. Create RESTful API routes for a product resource
3. Implement custom middleware for logging, authentication, and validation
4. Add comprehensive error handling
5. Develop advanced features like filtering, pagination, and search

## Getting Started

1. Accept the GitHub Classroom assignment invitation
2. Clone your personal repository that was created by GitHub Classroom
3. Install dependencies:
   ```
   npm install
   ```
4. Run the server:
   ```
   npm start
   ```

## Files Included

- `Week2-Assignment.md`: Detailed assignment instructions
- `server.js`: Starter Express.js server file
- `.env.example`: Example environment variables file

## Requirements

- Node.js (v18 or higher)
- npm or yarn
- Postman, Insomnia, or curl for API testing

## API Endpoints

The API will have the following endpoints:

- `GET /api/products`: Get all products
- `GET /api/products/:id`: Get a specific product
- `POST /api/products`: Create a new product
- `PUT /api/products/:id`: Update a product
- `DELETE /api/products/:id`: Delete a product

## Submission

Your work will be automatically submitted when you push to your GitHub Classroom repository. Make sure to:

1. Complete all the required API endpoints
2. Implement the middleware and error handling
3. Document your API in the README.md
4. Include examples of requests and responses

## Resources

- [Express.js Documentation](https://expressjs.com/)
- [RESTful API Design Best Practices](https://restfulapi.net/)
- [HTTP Status Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) 
.
├── controllers/
├── data/
├── errors/
├── middleware/
├── routes/
├── utils/
├── .env.example
├── .gitignore
├── package.json
├── README.md
└── server.js
npm install
cp .env.example .env
# then open .env and set:
# API_KEY=supersecretapikey
# PORT=3000
npm start
# List products (with pagination/filter)
curl "http://localhost:3000/api/products?category=collectibles&page=1&limit=1"

# Get by ID (replace :id with real id from list)
curl http://localhost:3000/api/products/a1

# Search
curl "http://localhost:3000/api/products/search?q=egg"

# Stats (count by category)
curl http://localhost:3000/api/products/stats

# Create (requires API key)
curl -X POST http://localhost:3000/api/products \
  -H "Content-Type: application/json" \
  -H "x-api-key: supersecretapikey" \
  -d '{"name":"Direwolf Plush","description":"Soft toy","price":19.99,"category":"merch","inStock":true}'

# Update (requires API key) — replace :id
curl -X PUT http://localhost:3000/api/products/:id \
  -H "Content-Type: application/json" \
  -H "x-api-key: supersecretapikey" \
  -d '{"name":"Direwolf Plush XL","description":"Bigger","price":24.99,"category":"merch","inStock":true}'

# Delete (requires API key) — replace :id
curl -X DELETE http://localhost:3000/api/products/:id \
  -H "x-api-key: supersecretapikey"
