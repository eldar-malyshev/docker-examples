# PHP & MySQL with Docker Compose

This project runs PHP and MySQL services using Docker Compose.

## Setup

1. Copy the example environment file:

```bash
cp .env.example .env
```

2. Edit `.env` with your MySQL credentials. **Do not commit this file to version control.**

```dotenv
MYSQL_ROOT_PASSWORD=root123
MYSQL_DATABASE=myapp
MYSQL_USER=user
MYSQL_PASSWORD=password123
```

## Running the Stack

Start the stack:
```bash
docker compose up
```

Stop the stack:
```bash
docker compose down
```

## Services

- **MySQL**: The database service storing your application data.
- **phpMyAdmin**: Accessible at http://localhost:8080/ for managing MySQL via a web interface.

## Network and Healthcheck

This setup uses an explicit Docker network named `app` to allow seamless communication between services. The `phpMyAdmin` service depends on the `MySQL` service being healthy before starting, ensuring reliable connectivit