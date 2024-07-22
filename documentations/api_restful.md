# RESTful API Documentation

Welcome to the RESTful API documentation! This document provides details on how to interact with the API, including endpoints, supported HTTP methods, parameters, and response examples.

## Table of Contents
- [Introduction](#introduction)
- [Authentication](#authentication)
- [Endpoints](#endpoints)
  - [Users](#users)
    - [Get Users](#get-users)
    - [Create User](#create-user)
    - [Get User by ID](#get-user-by-id)
    - [Update User](#update-user)
    - [Delete User](#delete-user)
  - [Projects](#projects)
    - [Get Projects](#get-projects)
    - [Create Project](#create-project)
    - [Get Project by ID](#get-project-by-id)
    - [Update Project](#update-project)
    - [Delete Project](#delete-project)
- [Common Errors](#common-errors)
- [Additional Resources](#additional-resources)

## Introduction
This RESTful API allows managing users and projects in a project management application. The API follows REST standards, using HTTP methods for CRUD (Create, Read, Update, Delete) operations.

## Authentication
To use the API, you need to authenticate using JWT (JSON Web Tokens).

> ℹ️ **Note:** Include the authentication token in the header of each request:
> ```
> Authorization: Bearer <your-jwt-token>
> ```

## Endpoints

### Users

#### Get Users
- **Endpoint:** `/api/users`
- **Method:** `GET`
- **Description:** Returns a list of all users.
- **Successful Response:**
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

#### Create User
- **Endpoint:** `/api/users`
- **Method:** `POST`
- **Description:** Creates a new user.
- **Request Body:**
  ```json
  {
    "name": "João Silva",
    "email": "joao.silva@example.com",
    "password": "password123"
  }
  ```
- **Successful Response:**
  ```json
  {
    "id": 1,
    "name": "João Silva",
    "email": "joao.silva@example.com"
  }
  ```

#### Get User by ID
- **Endpoint:** `/api/users/{id}`
- **Method:** `GET`
- **Description:** Returns details of a specific user.
- **URL Parameters:**
  - `id` (required): User ID
- **Successful Response:**
  ```json
  {
    "id": 1,
    "name": "João Silva",
    "email": "joao.silva@example.com"
  }
  ```

#### Update User
- **Endpoint:** `/api/users/{id}`
- **Method:** `PUT`
- **Description:** Updates the information of a specific user.
- **URL Parameters:**
  - `id` (required): User ID
- **Request Body:**
  ```json
  {
    "name": "João Silva",
    "email": "joao.silva@example.com",
    "password": "newPassword123"
  }
  ```
- **Successful Response:**
  ```json
  {
    "id": 1,
    "name": "João Silva",
    "email": "joao.silva@example.com"
  }
  ```

#### Delete User
- **Endpoint:** `/api/users/{id}`
- **Method:** `DELETE`
- **Description:** Deletes a specific user.
- **URL Parameters:**
  - `id` (required): User ID
- **Successful Response:**
  ```json
  {
    "message": "User successfully deleted"
  }
  ```

### Projects

#### Get Projects
- **Endpoint:** `/api/projects`
- **Method:** `GET`
- **Description:** Returns a list of all projects.
- **Successful Response:**
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

#### Create Project
- **Endpoint:** `/api/projects`
- **Method:** `POST`
- **Description:** Creates a new project.
- **Request Body:**
  ```json
  {
    "name": "Project A",
    "description": "Description of Project A"
  }
  ```
- **Successful Response:**
  ```json
  {
    "id": 1,
    "name": "Project A",
    "description": "Description of Project A"
  }
  ```

#### Get Project by ID
- **Endpoint:** `/api/projects/{id}`
- **Method:** `GET`
- **Description:** Returns details of a specific project.
- **URL Parameters:**
  - `id` (required): Project ID
- **Successful Response:**
  ```json
  {
    "id": 1,
    "name": "Project A",
    "description": "Description of Project A"
  }
  ```

#### Update Project
- **Endpoint:** `/api/projects/{id}`
- **Method:** `PUT`
- **Description:** Updates the information of a specific project.
- **URL Parameters:**
  - `id` (required): Project ID
- **Request Body:**
  ```json
  {
    "name": "Project A",
    "description": "Updated description of Project A"
  }
  ```
- **Successful Response:**
  ```json
  {
    "id": 1,
    "name": "Project A",
    "description": "Updated description of Project A"
  }
  ```

#### Delete Project
- **Endpoint:** `/api/projects/{id}`
- **Method:** `DELETE`
- **Description:** Deletes a specific project.
- **URL Parameters:**
  - `id` (required): Project ID
- **Successful Response:**
  ```json
  {
    "message": "Project successfully deleted"
  }
  ```

## Common Errors

### 400 Bad Request
- **Description:** The request contains invalid parameters or is malformed.
- **Response Example:**
  ```json
  {
    "error": "Invalid request. Please check the parameters and try again."
  }
  ```

### 401 Unauthorized
- **Description:** The request does not contain a valid authentication token.
- **Response Example:**
  ```json
  {
    "error": "Authentication required. Please provide a valid token."
  }
  ```

### 404 Not Found
- **Description:** The requested resource was not found.
- **Response Example:**
  ```json
  {
    "error": "Resource not found."
  }
  ```

### 500 Internal Server Error
- **Description:** An error occurred on the server.
- **Response Example:**
  ```json
  {
    "error": "Internal server error. Please try again later."
  }
  ```

## Additional Resources
- [Authentication Guide](#)
- [Complete API Documentation](#)
- [API Usage Examples](#)

---

We hope this documentation helps you integrate and use our RESTful API effectively. If you have any questions or need additional assistance, please do not hesitate to contact us.

Happy integrating!