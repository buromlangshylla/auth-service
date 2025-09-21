# Auth Service

This project is an authentication microservice for the Insurance Premium Calculator system. It is built using Django and Django REST Framework.

## Features
- User registration and authentication
- JWT-based token authentication

## Project Structure
- `auth_project/`: Django project configuration
- `accounts/`: Django app for user accounts
- `main.py`, `manage.py`: Entry points for running the service
- `requirements.txt`: Python dependencies
- `.gitignore`: Files and folders ignored by Git

## Setup
1. Create and activate a virtual environment:
   ```cmd
   python -m venv venv-auth
   venv-auth\Scripts\activate
   ```
2. Install dependencies:
   ```cmd
   pip install -r requirements.txt
   ```
3. Run migrations:
   ```cmd
   python manage.py migrate
   ```
4. Start the development server:
   ```cmd
   python manage.py runserver
   ```

## Usage
- Access API endpoints via `/accounts/` URLs.
- Use JWT tokens for authentication.

## Example API Usage

### Registration
- **URL:** `/auth/register/`
- **Method:** POST
- **Request Body:**
  ```json
  {
    "username": "string",
    "email": "string",
    "password": "string"
  }
  ```
- **Response:**
  ```json
  {
    "id": 1,
    "username": "string",
    "email": "string"
  }
  ```

### Login (JWT Token Obtain)
- **URL:** `/auth/login/`
- **Method:** POST
- **Request Body:**
  ```json
  {
    "username": "string",
    "password": "string"
  }
  ```
- **Response:**
  ```json
  {
    "refresh": "<refresh_token>",
    "access": "<access_token>"
  }
  ```

  ### Refresh Token (New Access Token Obtain)
- **URL:** `/auth/login/`
- **Method:** POST
- **Request Body:**
  ```json
  {
    "refresh": "string",
  }
  ```
- **Response:**
  ```json
  {
    "refresh": "<refresh_token>",
    "access": "<access_token>"
  }
  ```

### Get User Profile
- **URL:** `/auth/user/:id`
- **Method:** GET
- **Headers:**
  - `Authorization: Bearer <access_token>`
- **Response:**
  ```json
  {
    "id": 1,
    "username": "string",
    "email": "string"
  }
  ```

## Development
- Recommended IDE: PyCharm
- Python version: 3.12+

## Postman Collection
https://.postman.co/workspace/My-Workspace~198fa8b8-77fe-4e2d-806b-8fd72254351a/folder/46430376-02c13b25-c218-410e-8c66-35842ba80151?action=share&creator=46430376&ctx=documentation&active-environment=46430376-d2beb181-8c76-457f-abef-9c9dd95b265b
