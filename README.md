# FastAPI Social Media API

![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![PostgreSQL](https://img.shields.io/badge/postgresql-4169e1?style=for-the-badge&logo=postgresql&logoColor=white)

This is a comprehensive RESTful API for a social media platform built using **FastAPI** and **PostgreSQL**. 


## Features

- **User Authentication**: Secure JWT-based authentication for registering and logging in users.
- **Post Management**: 
  - Create, read, update, and delete (CRUD) posts.
  - Retrieve all posts or single posts by ID.
- **Voting System**: Like/upvote posts seamlessly.
- **Relational Database**: Leverages SQLAlchemy ORM for database operations with PostgreSQL.
- **Alembic**: Database migrations management.
- **Testing**: Comprehensive tests utilizing Pytest.
- **Deployment Ready**: Configurations provided for Docker, Nginx, and Gunicorn.

## API Routes

### 1) Authentication (`/login`)
- Authenticate user and receive a JWT token.

### 2) Users (`/users`)
- `POST /users/`: Create a new user.
- `GET /users/{id}`: Retrieve a user by ID.

### 3) Posts (`/posts`)
- `GET /posts/`: Retrieve a list of posts.
- `GET /posts/{id}`: Retrieve a specific post.
- `POST /posts/`: Create a new post.
- `PUT /posts/{id}`: Update an existing post.
- `DELETE /posts/{id}`: Delete a post.

### 4) Votes (`/vote`)
- `POST /vote/`: Vote on a post. 

## Getting Started

### Prerequisites
- Python 3.8+
- PostgreSQL database

### Local Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/amarn/fastapi-course.git
   cd fastapi-course
   ```

2. **Install Dependencies**
   It's recommended to create a virtual environment first.
   ```bash
   pip install -r requirements.txt
   ```

3. **Database Configuration**
   Create a database in PostgreSQL. Then, create a `.env` file in the root directory and add your configurations:
   ```env
   DATABASE_HOSTNAME=localhost
   DATABASE_PORT=5432
   DATABASE_PASSWORD=your_password
   DATABASE_NAME=your_db_name
   DATABASE_USERNAME=your_username
   SECRET_KEY=generate_a_random_secret_key_here
   ALGORITHM=HS256
   ACCESS_TOKEN_EXPIRE_MINUTES=60
   ```
   *Note: You can generate a secure secret key using `openssl rand -hex 32`.*

4. **Run the Application**
   ```bash
   uvicorn app.main:app --reload
   ```

5. **Explore the API Documentation**
   FastAPI automatically generates interactive API documentation.
   - Swagger UI: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
   - ReDoc: [http://127.0.0.1:8000/redoc](http://127.0.0.1:8000/redoc)

## Deployment
This project includes configurations for deployment:
- `Dockerfile` & `docker-compose-*.yml` for containerization.
- `nginx` config file.
- `gunicorn.service` file for daemonizing the application.
