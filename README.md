---

# Employee Management System

The Employee Management System is a full-stack application designed to manage employee details. It provides a user-friendly interface to add and view employee records, supported by a robust backend API and a dynamic frontend.

---

## Table of Contents
1. [Overview](#overview)
2. [Project Architecture](#project-architecture)
3. [Technologies Used](#technologies-used)
4. [Setup and Deployment](#setup-and-deployment)
    - [Backend](#backend)
    - [Frontend](#frontend)
    - [Database](#database)
    - [Docker Compose](#docker-compose)
5. [CI/CD Pipeline](#cicd-pipeline)
6. [Contributing](#contributing)
7. [License](#license)

---

## Overview

This system enables organizations to manage employee information efficiently. It features:
- A **ReactJS frontend** for interactive user interfaces.
- A **Golang backend** for high-performance API endpoints.
- A **PostgreSQL database** to store employee data securely.

---

## Project Architecture

```
├── backend/      # Contains Golang source code for API
├── frontend/     # Contains ReactJS code for the web interface
├── postgres_data/ # Volume for persistent PostgreSQL storage
├── docker-compose.yml  # Docker Compose configuration
├── Jenkinsfile   # CI/CD pipeline configuration
```

---

## Technologies Used
- **Backend**: Golang 1.19
- **Frontend**: ReactJS
- **Database**: PostgreSQL 13
- **Containerization**: Docker, Docker Compose
- **CI/CD**: Jenkins

---

## Setup and Deployment

### Backend
1. Install Golang 1.19.
2. Navigate to the `backend/` directory.
3. Run:
   ```bash
   go get ./...
   DB_HOST=<POSTGRES_HOST> DB_USER=<POSTGRES_USER> DB_PASSWORD=<POSTGRES_PASSWORD> \
   DB_NAME=<POSTGRES_DB_NAME> DB_PORT=<POSTGRES_PORT> ALLOWED_ORIGINS=<ALLOWED_ORIGINS> \
   go run main.go
   ```
4. Backend server starts on port **8080**.

---

### Frontend
1. Install Node.js version 14.17.0.
2. Navigate to the `frontend/` directory.
3. Run:
   ```bash
   npm install
   npm start
   ```
4. Frontend server starts on port **3000**.

---

### Database
1. PostgreSQL is used for database management.
2. Ensure the following environment variables are configured:
   - `POSTGRES_DB`
   - `POSTGRES_USER`
   - `POSTGRES_PASSWORD`
   - `POSTGRES_PORT`

---

### Docker Compose
1. Ensure Docker and Docker Compose are installed.
2. To build and start all services (backend, frontend, database):
   ```bash
   docker-compose up --build
   ```
3. Access the services:
   - Frontend: `http://localhost:3000`
   - Backend: `http://localhost:8080`

---

## CI/CD Pipeline

The project uses Jenkins for CI/CD with the following steps:
1. **Checkout**: Clones the repository.
2. **Build and Deploy**: Runs `docker-compose up` to build and deploy services.
3. **Cleanup**: Runs `docker-compose down` to stop services post-deployment.

Refer to the `Jenkinsfile` for detailed configuration.

---

## Contributing

Contributions are welcome! To contribute:
1. Fork this repository.
2. Create a new branch for your feature or bugfix.
3. Submit a pull request with a detailed description of your changes.

---

## License

This project is licensed under the MIT License. See `LICENSE` for more details.

---
