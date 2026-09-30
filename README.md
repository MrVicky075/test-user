# User App (Spring Boot + Thymeleaf + PostgreSQL)

Simple app to **create** and **list** users. No edit or delete.

## Requirements

- Java 17+
- Maven 3.8+
- PostgreSQL running locally

## Database setup

Create the database:

```sql
CREATE DATABASE userdb;
```

Default connection in `src/main/resources/application.properties`:

- URL: `jdbc:postgresql://localhost:5432/userdb`
- Username: `postgres`
- Password: `postgres`

Update these if your PostgreSQL credentials differ.

## Run

```bash
mvn spring-boot:run
```

Open: http://localhost:8080/users

## UI

| Page | URL |
|------|-----|
| User list | http://localhost:8080/users |
| Create user | http://localhost:8080/users/new |

## API

| Method | URL | Description |
|--------|-----|-------------|
| GET | `/api/users` | List all users |
| POST | `/api/users` | Create a user |

### Create user (example)

```bash
curl -X POST http://localhost:8080/api/users ^
  -H "Content-Type: application/json" ^
  -d "{\"name\":\"Mahesh\",\"email\":\"mahesh@example.com\"}"
```

### List users (example)

```bash
curl http://localhost:8080/api/users
```
