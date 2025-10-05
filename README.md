# NestJS Trello Lite

A collaborative task management application built with **NestJS**, covering a wide range of features including authentication, authorization, validation, error handling, logging, WebSockets, and more. This project is designed to help you learn **all core concepts of NestJS** at a basic-to-intermediate level.

---

## **Features**

- **User Authentication & Authorization**
  - JWT-based authentication
  - Role-based access control (Admin/User)
- **CRUD Operations**
  - Users, Projects, Tasks
- **Validation & Transformation**
  - DTOs and Pipes for request validation
- **Error Handling**
  - Global HTTP exception filters
- **Logging & Interceptors**
  - Request/response logging and performance monitoring
- **Real-time Updates**
  - WebSocket notifications for task updates
- **Configuration**
  - `.env` support via ConfigModule
- **Database Integration**
  - TypeORM / Prisma with PostgreSQL or MySQL
- **Testing**
  - Unit and e2e tests using Jest

---

## **Prerequisites**

- Node.js >= 18
- npm or yarn
- PostgreSQL or MySQL
- NestJS CLI (`npm i -g @nestjs/cli`)
- Basic understanding of TypeScript, REST APIs, and WebSockets

---

## **Installation**

```bash
# Clone the repository
git clone <repository-url>
cd nestjs-task-app

# Install dependencies
npm install
Configuration
Copy .env.example to .env:

bash
Copy code
cp .env.example .env
Fill in the necessary environment variables:

env
Copy code
# Example
DATABASE_HOST=localhost
DATABASE_PORT=5432
DATABASE_USER=your_db_user
DATABASE_PASSWORD=your_db_password
DATABASE_NAME=nestjs_task_db
JWT_SECRET=your_jwt_secret
JWT_EXPIRATION=3600s
Running the App
bash
Copy code
# Development mode
npm run start:dev

# Production mode
npm run build
npm run start:prod
The app will run on http://localhost:3000 by default.

Folder Structure
bash
Copy code
src/
├─ app.module.ts
├─ main.ts
├─ config/               # Configuration module and service
├─ common/               # Global filters, interceptors, pipes, decorators, guards
├─ auth/                 # Authentication & authorization
├─ users/                # User CRUD, role management
├─ projects/             # Projects module
├─ tasks/                # Tasks module
├─ notifications/        # WebSocket gateway for real-time updates
└─ shared/               # Constants, interfaces, helpers
API Endpoints
Auth

POST /auth/register → Register new user

POST /auth/login → Login user

Users

GET /users → List all users (Admin only)

GET /users/:id → Get user by ID

PATCH /users/:id → Update user

DELETE /users/:id → Delete user

Projects

GET /projects → List all projects

POST /projects → Create a project

PATCH /projects/:id → Update a project

DELETE /projects/:id → Delete a project

Tasks

GET /tasks → List all tasks

POST /tasks → Create a task

PATCH /tasks/:id → Update a task

DELETE /tasks/:id → Delete a task

WebSockets

Real-time task notifications via notifications.gateway.ts

Testing
Unit Tests

bash
Copy code
npm run test
E2E Tests

bash
Copy code
npm run test:e2e
