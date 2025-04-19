# Programming Task App 

## System Architecture

The application consists of two main parts:

1. **Backend**: Spring Boot application with:
   - User authentication with JWT
   - RESTful API endpoints for tasks and submissions
   - Integration with Supabase PostgreSQL database
   - Code evaluation system

2. **Frontend**: React application with:
   - User registration and login
   - Task listing with filtering and pagination
   - Task details view
   - Solution submission
   - Submission history and results

## Setup Instructions

### Backend Setup

1. Navigate to the backend directory:
   ```
   cd /home/ubuntu/spoj-system/backend
   ```

2. Build the application:
   ```
   ./mvnw clean package
   ```

3. Run the application:
   ```
   java -jar target/spoj-system-0.0.1-SNAPSHOT.jar
   ```

The backend will start on port 8080.

### Supabase Setup

Follow the instructions in the `supabase-setup-guide.md` file to:
1. Create a Supabase account
2. Set up a new project
3. Configure the database connection
4. Apply the database schema

### Frontend Setup

1. Navigate to the frontend directory:
   ```
   cd /home/ubuntu/spoj-system/frontend/spoj-frontend
   ```

2. Install dependencies:
   ```
   pnpm install
   ```

3. Start the development server:
   ```
   pnpm run dev
   ```

The frontend will start on port 3000.

## Environment Configuration

### Backend Environment Variables

Create a `.env` file in the backend directory with the following variables:

```
SUPABASE_HOST=your-project-id.supabase.co
SUPABASE_PORT=5432
SUPABASE_DB=postgres
SUPABASE_USER=postgres
SUPABASE_PASSWORD=your-database-password
JWT_SECRET=your-jwt-secret
SPRING_MAIL_HOST=smtp.example.com
SPRING_MAIL_PORT=587
SPRING_MAIL_USERNAME=your-email@example.com
SPRING_MAIL_PASSWORD=your-email-password
SPRING_MAIL_PROPERTIES_MAIL_SMTP_AUTH=true
SPRING_MAIL_PROPERTIES_MAIL_SMTP_STARTTLS_ENABLE=true
APP_URL=http://localhost:3000
```

### Frontend Environment Variables

Create a `.env` file in the frontend directory with:

```
REACT_APP_API_URL=http://localhost:8080/api
```

## Key Features

- **User Management**: Registration, email confirmation, and login
- **Task Management**: Browse, filter, and view programming tasks
- **Submission System**: Submit solutions in multiple languages (Python, JavaScript, Java, C++)
- **Evaluation**: Automatic evaluation of submitted code
- **Results Tracking**: View submission history and results

## API Documentation

### Authentication Endpoints

- `POST /api/auth/register` - Register a new user
- `GET /api/auth/confirm/{token}` - Confirm email address
- `POST /api/auth/login` - Login and get JWT token

### Task Endpoints

- `GET /api/tasks` - Get all tasks with pagination and filtering
- `GET /api/tasks/{id}` - Get a specific task
- `POST /api/tasks/seed` - Create sample tasks

### Submission Endpoints

- `POST /api/submissions` - Submit a solution
- `GET /api/submissions/user` - Get current user's submissions
- `GET /api/submissions/task/{taskId}` - Get submissions for a specific task
- `GET /api/submissions/{id}` - Get a specific submission

## Database Schema

The application uses three main tables:

1. **users** - Stores user information and authentication details
2. **tasks** - Stores programming tasks with details and constraints
3. **submissions** - Stores user submissions with evaluation results


