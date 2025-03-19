# Cloud-Native User Authentication Service

A robust, cloud-native user authentication service built with Django REST Framework, designed for CSYE-6225 Network Structures and Cloud Computing (Spring 2024).

## Features

- User Authentication and Authorization
- RESTful API Endpoints
- PostgreSQL Database Integration
- Health Check Endpoint
- Cloud-Native Architecture
- Serverless Microservice Support
- Comprehensive Test Coverage

## Tech Stack

- **Backend Framework**: Django 4.x
- **API Framework**: Django REST Framework
- **Database**: PostgreSQL
- **Authentication**: JWT (JSON Web Tokens)
- **Cloud Services**: Google Cloud Platform
- **Testing**: pytest
- **Documentation**: drf-yasg (Swagger/OpenAPI)

## Prerequisites

- Python 3.x
- Pipenv
- PostgreSQL
- Google Cloud Platform Account (for cloud deployment)

## Installation

1. Install Pipenv:
```bash
pip install pipenv
```

2. Clone the repository:
```bash
git clone https://github.com/shreyagupta30/webapp-csye6225.git
cd webapp-csye6225
```

3. Activate the virtual environment:
```bash
pipenv shell
```

4. Install dependencies:
```bash
pipenv install
```

## Database Setup

1. Create a PostgreSQL database:
```sql
CREATE DATABASE your_database_name;
```

2. Grant privileges:
```sql
GRANT ALL PRIVILEGES ON your_database_name TO your_username;
```

3. Configure environment variables:
Create a `.env` file in the root directory:
```bash
DEBUG='True'
DB_HOST=localhost
DB_NAME=<your_database_name>
DB_USER=<your_username>
DB_PASSWORD=<your_password>
DB_PORT=5432
```

## Running the Application

1. Apply database migrations:
```bash
python manage.py makemigrations
python manage.py migrate
```

2. Start the development server:
```bash
python manage.py runserver
```

## API Endpoints

### Health Check
```http
GET /healthz
```
Returns HTTP 200 if the service is healthy.

### User Authentication

#### Create User
```http
POST /v1/user
Content-Type: application/json

{
    "username": "user@example.com",
    "firstname": "John",
    "lastname": "Doe",
    "password": "secure_password"
}
```

#### Get User Profile
```http
GET /v1/user/self
Authorization: Bearer <jwt_token>
```

#### Update User Profile
```http
PUT /v1/user/self
Authorization: Bearer <jwt_token>
Content-Type: application/json

{
    "firstname": "John",
    "lastname": "Smith",
    "password": "new_password"
}
```

## Testing

Run the test suite:
```bash
pytest
```

## Cloud Deployment

The application is designed for cloud deployment with the following features:
- Packer configuration for AMI creation
- GitHub Actions for CI/CD
- Serverless microservice support
- Health check monitoring

## Security Considerations

- Passwords are hashed using bcrypt
- JWT-based authentication
- Environment variable configuration for sensitive data
- Input validation and sanitization

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is part of the CSYE-6225 course at Northeastern University.

## References

- [Django Documentation](https://docs.djangoproject.com/)
- [Django REST Framework](https://www.django-rest-framework.org/)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- [Google Cloud Documentation](https://cloud.google.com/docs)
