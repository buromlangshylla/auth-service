# Auth Service

This project is an authentication microservice for the Insurance Premium Calculator system. It is built using Django and Django REST Framework.

## Features
- User registration and authentication
- JWT-based token authentication
- Account management endpoints

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
- **URL:** `/accounts/register/`
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
- **URL:** `/accounts/token/`
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

### Get User Profile
- **URL:** `/accounts/profile/`
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

