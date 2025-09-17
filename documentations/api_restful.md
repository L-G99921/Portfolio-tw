# RESTful API Documentation

This documentation provides comprehensive details for interacting with our RESTful API, including endpoints, HTTP methods, parameters, and response examples.

## Table of Contents

- [Introduction](#introduction)
- [Authentication](#authentication)
- [Endpoints](#endpoints)
  - [Users](#users)
    - [Get users](#get-users)
    - [Create user](#create-user)
    - [Get user by ID](#get-user-by-id)
    - [Update user](#update-user)
    - [Delete user](#delete-user)
  - [Projects](#projects)
    - [Get projects](#get-projects)
    - [Create project](#create-project)
    - [Get project by ID](#get-project-by-id)
    - [Update project](#update-project)
    - [Delete project](#delete-project)
- [Error handling](#error-handling)
- [Additional resources](#additional-resources)

## Introduction

Our RESTful API enables you to manage users and projects in a comprehensive project management application. The API follows REST standards and uses standard HTTP methods for CRUD (Create, Read, Update, Delete) operations.

## Authentication

To use this API, authenticate by using JWT (JSON Web Tokens).

**Important**: Include the authentication token in the header of each request:

```http
Authorization: Bearer <your-jwt-token>
```

## Endpoints

### Users

#### Get users
- **Endpoint**: `/api/users`
- **Method**: `GET`
- **Description**: Returns a list of all users.
- **Successful response**:
  ```json
  [
    {
      "id": 1,
      "name": "João Silva",
      "email": "joao.silva@example.com"
    },
    {
      "id": 2,
      "name": "Maria Souza",
      "email": "maria.souza@example.com"
    }
  ]
  ```

#### Create user
- **Endpoint**: `/api/users`
- **Method**: `POST`
- **Description**: Creates a new user.
- **Request body**:
  ```json
  {
    "name": "João Silva",
    "email": "joao.silva@example.com",
    "password": "password123"
  }
  ```
- **Successful response**:
  ```json
  {
    "id": 1,
    "name": "João Silva",
    "email": "joao.silva@example.com"
  }
  ```

#### Get user by ID
- **Endpoint**: `/api/users/{id}`
- **Method**: `GET`
- **Description**: Returns details of a specific user.
- **URL parameters**:
  - `id` (required): User ID
- **Successful response**:
  ```json
  {
    "id": 1,
    "name": "João Silva",
    "email": "joao.silva@example.com"
  }
  ```

#### Update user
- **Endpoint**: `/api/users/{id}`
- **Method**: `PUT`
- **Description**: Updates the information of a specific user.
- **URL parameters**:
  - `id` (required): User ID
- **Request body**:
  ```json
  {
    "name": "João Silva",
    "email": "joao.silva@example.com",
    "password": "newPassword123"
  }
  ```
- **Successful response**:
  ```json
  {
    "id": 1,
    "name": "João Silva",
    "email": "joao.silva@example.com"
  }
  ```

#### Delete user
- **Endpoint**: `/api/users/{id}`
- **Method**: `DELETE`
- **Description**: Deletes a specific user.
- **URL parameters**:
  - `id` (required): User ID
- **Successful response**:
  ```json
  {
    "message": "User successfully deleted"
  }
  ```

### Projects

#### Get projects
- **Endpoint**: `/api/projects`
- **Method**: `GET`
- **Description**: Returns a list of all projects.
- **Successful response**:
  ```json
  [
    {
      "id": 1,
      "name": "Project A",
      "description": "Description of Project A"
    },
    {
      "id": 2,
      "name": "Project B",
      "description": "Description of Project B"
    }
  ]
  ```

#### Create project
- **Endpoint**: `/api/projects`
- **Method**: `POST`
- **Description**: Creates a new project.
- **Request body**:
  ```json
  {
    "name": "Project A",
    "description": "Description of Project A"
  }
  ```
- **Successful response**:
  ```json
  {
    "id": 1,
    "name": "Project A",
    "description": "Description of Project A"
  }
  ```

#### Get project by ID
- **Endpoint**: `/api/projects/{id}`
- **Method**: `GET`
- **Description**: Returns details of a specific project.
- **URL parameters**:
  - `id` (required): Project ID
- **Successful response**:
  ```json
  {
    "id": 1,
    "name": "Project A",
    "description": "Description of Project A"
  }
  ```

#### Update project
- **Endpoint**: `/api/projects/{id}`
- **Method**: `PUT`
- **Description**: Updates the information of a specific project.
- **URL parameters**:
  - `id` (required): Project ID
- **Request body**:
  ```json
  {
    "name": "Project A",
    "description": "Updated description of Project A"
  }
  ```
- **Successful response**:
  ```json
  {
    "id": 1,
    "name": "Project A",
    "description": "Updated description of Project A"
  }
  ```

#### Delete project
- **Endpoint**: `/api/projects/{id}`
- **Method**: `DELETE`
- **Description**: Deletes a specific project.
- **URL parameters**:
  - `id` (required): Project ID
- **Successful response**:
  ```json
  {
    "message": "Project successfully deleted"
  }
  ```

## Error handling

### 400 Bad Request
- **Description**: The request contains invalid parameters or is malformed.
- **Response Example:**
  ```json
  {
    "error": "Invalid request. Please check the parameters and try again."
  }
  ```

### 401 Unauthorized
- **Description**: The request doesn't contain a valid authentication token.
- **Response Example:**
  ```json
  {
    "error": "Authentication required. Please provide a valid token."
  }
  ```

### 404 Not Found
- **Description**: The requested resource wasn't found.
- **Response Example:**
  ```json
  {
    "error": "Resource not found."
  }
  ```

### 500 Internal Server Error
- **Description**: An error occurred on the server.
- **Response Example:**
  ```json
  {
    "error": "Internal server error. Please try again later."
  }
  ```

## Additional resources
- [Authentication Guide](#)
- [Complete API Documentation](#)
- [API Usage Examples](#)

---

This documentation helps you integrate and use our RESTful API effectively. If you have questions or need assistance, contact our support team.

Happy integrating!