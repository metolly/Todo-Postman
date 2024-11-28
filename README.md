Todo Postman Project README Project Overview The Todo Postman Project is a RESTful API testing project designed for managing "To-Do" items. The project includes requests for user registration, authentication, and CRUD (Create, Read, Update, Delete) operations on To-Do items. This guide provides a clear explanation of the project's structure, endpoints, and usage.

Requirements Postman: To execute and test API requests. Server/API: A functional server hosting the To-Do API (e.g., a Node.js/Express server, Django backend, etc.). Access Token Management: The access token is stored after login to authenticate subsequent requests. API Endpoints

    User Registration Registers a new user.

Endpoint: /api/register Method: POST Request Headers: Content-Type: application/json Request Body: json Copy code { "username": "newuser", "email": "newuser@example.com", "password": "securepassword" } Response: json Copy code { "message": "User registered successfully", "userId": "12345" } 2. User Login Authenticates the user and provides an access token.

Endpoint: /api/login Method: POST Request Headers: Content-Type: application/json Request Body: json Copy code { "email": "newuser@example.com", "password": "securepassword" } Response: json Copy code { "accessToken": "eyJhbGciOiJIUzI1NiIsInR...", "message": "Login successful" } ⚠️ Note: Save the accessToken for use in future requests requiring authorization.

    Add a New To-Do Creates a new to-do item.

Endpoint: /api/todos Method: POST Request Headers: Content-Type: application/json Authorization: Bearer Request Body: json Copy code { "title": "Buy groceries", "description": "Milk, Eggs, Bread" } Response: json Copy code { "todoId": "78910", "message": "To-Do item created successfully" } 4. Get a Specific To-Do Fetches details of a specific to-do item.

Endpoint: /api/todos/{todoId} Method: GET Request Headers: Authorization: Bearer Response: json Copy code { "todoId": "78910", "title": "Buy groceries", "description": "Milk, Eggs, Bread", "status": "pending" } 5. Update a Specific To-Do Updates details of a specific to-do item.

Endpoint: /api/todos/{todoId} Method: PUT Request Headers: Content-Type: application/json Authorization: Bearer Request Body: json Copy code { "title": "Buy groceries and snacks", "description": "Milk, Eggs, Bread, Chips", "status": "in-progress" } Response: json Copy code { "todoId": "78910", "message": "To-Do item updated successfully" } 6. Delete a Specific To-Do Deletes a specific to-do item.

Endpoint: /api/todos/{todoId} Method: DELETE Request Headers: Authorization: Bearer Response: json Copy code { "message": "To-Do item deleted successfully" } Workflow in Postman Register a User: Send a POST request to /api/register with user details. Login to Obtain Access Token: Use the /api/login endpoint to log in and save the returned accessToken. In Postman, store the accessToken in the environment for easy access. CRUD Operations on To-Dos: Use the stored accessToken in the Authorization header for all requests related to To-Dos. Environment Variables (Postman) Set up the following environment variables in Postman for easier testing:

Variable Name Value Example baseUrl API base URL http://localhost:3000/api accessToken User token eyJhbGciOiJIUzI1NiIsInR... Testing the API Create a Collection: Create a new Postman collection for the project. Add Requests: Add requests for each endpoint mentioned above. Set Up Authorization: Use the accessToken variable in the Authorization tab for authorized requests. Conclusion This project demonstrates how to effectively manage a To-Do API using Postman. With a proper structure and reusable requests, this setup simplifies API testing and promotes efficiency.
