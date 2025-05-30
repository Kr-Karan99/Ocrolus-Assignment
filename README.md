# Content Management System (CMS)

A full-stack Content Management System built with Spring Boot and React.js.

## Tech Stack

### Backend
- Java 17
- Spring Boot 3.1.5
- Spring Security with JWT
- Spring Data JPA
- MySQL Database
- JUnit 5 & Mockito for testing

### Frontend
- React.js
- Material-UI (MUI)
- React Router
- Axios
- Context API for state management

## Prerequisites

- Java 17 or higher
- Node.js 16 or higher
- MySQL 8.0 or higher
- Docker and Docker Compose (optional)

## Project Structure

```
cms/
├── backend/           # Spring Boot backend
├── frontend/         # React.js frontend
├── docker-compose.yml
└── README.md
```

## Quick Start with Docker

1. Clone the repository:
```bash
git clone <repository-url>
cd cms
```

2. Configure database credentials:
   - Open `docker-compose.yml` and modify the MySQL environment variables if needed:
     ```yaml
     MYSQL_ROOT_PASSWORD: your_password
     MYSQL_DATABASE: cms
     ```
   - Open `backend/src/main/resources/application.properties` and update database credentials accordingly:
     ```properties
     spring.datasource.username=root
     spring.datasource.password=your_password
     ```

3. Run with Docker Compose:
```bash
docker-compose up --build
```

The application will be available at:
- Frontend: http://localhost:3000
- Backend API: http://localhost:8080
- MySQL: localhost:3306

## Manual Setup

### Backend Setup

1. Configure MySQL:
   - Create a database named 'cms'
   - Update `backend/src/main/resources/application.properties` with your MySQL credentials

2. Run the backend:
```bash
cd backend
./mvnw spring-boot:run
```

### Frontend Setup

1. Install dependencies:
```bash
cd frontend
npm install
```

2. Run the frontend:
```bash
npm start
```

## API Documentation

### Authentication Endpoints
- POST `/api/auth/register` - Register new user
- POST `/api/auth/login` - Login user

### Article Endpoints
- GET `/api/articles` - Get all articles (paginated)
- GET `/api/articles/{id}` - Get article by ID
- POST `/api/articles` - Create new article
- PUT `/api/articles/{id}` - Update article
- DELETE `/api/articles/{id}` - Delete article
- GET `/api/articles/recent` - Get recently viewed articles

## Security

- JWT-based authentication
- Password encryption using BCrypt
- Role-based authorization
- CORS configuration for frontend integration

## Database Schema

The application uses MySQL with the following main tables:
- users
- articles
- recently_viewed_articles

Database migrations are handled by Flyway.

## Environment Variables

### Backend
```properties
# application.properties
spring.datasource.url=jdbc:mysql://localhost:3306/cms
spring.datasource.username=your_username
spring.datasource.password=your_password
app.jwt.secret=your_jwt_secret
app.jwt.expiration=86400000
```

### Frontend
```env
# .env
REACT_APP_API_URL=http://localhost:8080
```
![Screenshot 2025-05-30 110818](https://github.com/user-attachments/assets/48e3aa54-a253-4928-b62f-b24b20a58dd7)
![Screenshot 2025-05-30 110841](https://github.com/user-attachments/assets/b1243b9e-2017-4a9b-a949-891e6ae3332d)
![Screenshot 2025-05-30 110941](https://github.com/user-attachments/assets/6da87ef7-d55d-4fdf-97fa-df519cfbf76c)
![Screenshot 2025-05-30 111010](https://github.com/user-attachments/assets/8840f25d-1bad-4b1c-91c6-ae6f8c39df87)
