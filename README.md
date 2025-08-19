# LMS_MVP
# Leave Management System 🏢

A comprehensive Leave Management System built with the MERN stack (MongoDB, Express.js, React, Node.js) for startups and small-to-medium businesses. This system handles employee onboarding, leave applications, approval workflows, and balance tracking with a focus on scalability and user experience.

## 🚀 Features

### Core Functionality
- ✅ **Employee Management**: Add, update, and manage employee records
- ✅ **Leave Applications**: Apply for different types of leave (annual, sick, personal, emergency)
- ✅ **Approval Workflow**: Multi-level approval system with manager delegation
- ✅ **Leave Balance Tracking**: Real-time balance calculation with pro-rated allocations
- ✅ **Dashboard Views**: Role-based dashboards for employees, managers, and HR
- ✅ **Audit Trail**: Complete history of all leave transactions

### Advanced Features
- 🔄 **Real-time Notifications**: Email and in-app notifications
- 📱 **Mobile Responsive**: Works seamlessly on all devices
- 🚫 **Conflict Detection**: Prevents overlapping leave requests
- 📊 **Analytics & Reporting**: Leave patterns and team analytics
- 🔒 **Role-based Access Control**: Secure access based on user roles
- 📅 **Calendar Integration**: Sync with popular calendar applications

## 🛠️ Tech Stack

### Frontend
- **React 18** - Modern UI library with hooks
- **Axios** - HTTP client for API communication
- **Tailwind CSS** - Utility-first CSS framework
- **React Router** - Client-side routing

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web application framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB object modeling
- **JWT** - JSON Web Token for authentication
- **Nodemailer** - Email notifications

### DevOps & Scaling
- **Docker** - Containerization
- **Nginx** - Load balancer and reverse proxy
- **Redis** - Caching and session storage
- **PM2** - Process manager for Node.js

## 📋 Prerequisites

Before running this application, make sure you have:

- **Node.js** (v16 or higher)
- **MongoDB** (v5.0 or higher)
- **npm** or **yarn** package manager
- **Git** for version control

## 🚀 Quick Start

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/leave-management-system.git
cd leave-management-system
```

### 2. Setup Backend
```bash
# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Create environment file
cp .env.example .env

# Update .env with your configuration
# MONGODB_URI=mongodb://localhost:27017/leave_management
# JWT_SECRET=your_jwt_secret_key
# EMAIL_HOST=smtp.gmail.com
# EMAIL_USER=your-email@gmail.com
# EMAIL_PASS=your-app-password

# Start MongoDB service
# On macOS: brew services start mongodb-community
# On Ubuntu: sudo systemctl start mongod
# On Windows: net start MongoDB

# Run database migrations (optional)
npm run migrate

# Start the server
npm run dev
```

### 3. Setup Frontend
```bash
# Open new terminal and navigate to frontend
cd frontend

# Install dependencies
npm install

# Create environment file
cp .env.example .env

# Update .env with backend URL
# REACT_APP_API_URL=http://localhost:5000/api

# Start the development server
npm start
```

### 4. Access the Application
- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:5000
- **API Documentation**: http://localhost:5000/api-docs (if Swagger is configured)

## 📁 Project Structure

```
leave-management-system/
├── backend/
│   ├── config/
│   │   ├── database.js
│   │   └── email.js
│   ├── controllers/
│   │   ├── employeeController.js
│   │   ├── leaveController.js
│   │   └── authController.js
│   ├── middleware/
│   │   ├── auth.js
│   │   ├── validation.js
│   │   └── errorHandler.js
│   ├── models/
│   │   ├── Employee.js
│   │   ├── Leave.js
│   │   └── LeaveBalance.js
│   ├── routes/
│   │   ├── employees.js
│   │   ├── leaves.js
│   │   └── auth.js
│   ├── .env.example
│   ├── package.json
│   └── server.js
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── common/
│   │   │   ├── employee/
│   │   │   ├── leave/
│   │   │   └── dashboard/
│   │   ├── App.js
│   │   └── index.js
│   ├── .env.example
│   └── package.json
├── README.md
└── .gitignore
```

## 🔧 Configuration

#### Frontend (.env)
```env
# API Configuration
REACT_APP_API_URL=http://localhost:5000/api
REACT_APP_APP_NAME=Leave Management System

# Feature Flags
REACT_APP_ENABLE_NOTIFICATIONS=true
REACT_APP_ENABLE_CALENDAR_SYNC=false
```

## 📚 API Documentation

### Authentication
```http
POST /api/auth/login
POST /api/auth/register
POST /api/auth/logout
GET  /api/auth/me
```

### Employees
```http
GET    /api/employees          # Get all employees
POST   /api/employees          # Add new employee
GET    /api/employees/:id      # Get employee by ID
PUT    /api/employees/:id      # Update employee
DELETE /api/employees/:id      # Delete employee
```

### Leave Management
```http
GET    /api/leaves                    # Get all leaves
POST   /api/leaves                    # Apply for leave
GET    /api/leaves/:id                # Get leave details
PUT    /api/leaves/:id/approve        # Approve leave
PUT    /api/leaves/:id/reject         # Reject leave
GET    /api/leaves/employee/:id       # Get employee's leaves
GET    /api/leaves/balance/:employeeId # Get leave balance
```

### Example API Requests

#### Add Employee
```bash
curl -X POST http://localhost:5000/api/employees \
  -H "Content-Type: application/json" \
  -d '{
    "name": "John Doe",
    "email": "john.doe@company.com",
    "department": "Engineering",
    "joiningDate": "2024-01-15"
  }'
```

#### Apply for Leave
```bash
curl -X POST http://localhost:5000/api/leaves \
  -H "Content-Type: application/json" \
  -d '{
    "employeeId": "60f7b3b3b3b3b3b3b3b3b3b3",
    "leaveType": "annual",
    "startDate": "2024-12-25",
    "endDate": "2024-12-27",
    "reason": "Christmas vacation"
  }'
```

## 🔧 Development

### Running Tests
```bash
# Backend tests
cd backend
npm test

# Frontend tests
cd frontend
npm test

# Run all tests
npm run test:all
```

### Code Quality
```bash
# Linting
npm run lint

# Formatting
npm run format

# Type checking (if using TypeScript)
npm run type-check
```

### Database Operations
```bash
# Seed database with sample data
npm run seed

# Reset database
npm run db:reset

# Create database backup
npm run db:backup

# Restore from backup
npm run db:restore backup-file.json
```




## 📈 Scaling & Performance

### Performance Optimization
- **Database Indexing**: Strategic indexes on frequently queried fields
- **Caching**: Redis for session data and frequently accessed information
- **Connection Pooling**: Efficient database connection management
- **Compression**: Gzip compression for API responses

### Scaling Strategy
1. **Horizontal Scaling**: Load balancers with multiple backend instances
2. **Database Replication**: Master-slave setup for read scaling
3. **Microservices**: Split into employee, leave, and notification services

### Monitoring
```bash
# Install monitoring tools
npm install --save-dev clinic autocannon

# Performance profiling
npm run profile

# Load testing
npm run load-test
```

## 🔒 Security Features

- **Authentication**: JWT-based authentication with secure cookies
- **Authorization**: Role-based access control (RBAC)
- **Input Validation**: Comprehensive request validation using Joi
- **Rate Limiting**: Prevent API abuse with rate limiting
- **CORS**: Configured Cross-Origin Resource Sharing
- **Helmet**: Security headers for Express applications
- **Data Sanitization**: MongoDB injection prevention


## 🤝 Contributing

### Development Workflow
1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Make your changes following the coding standards
4. Write tests for new features
5. Ensure all tests pass: `npm test`
6. Commit with conventional commits: `git commit -m "feat: add amazing feature"`
7. Push to your fork: `git push origin feature/amazing-feature`
8. Create a Pull Request

### Coding Standards
- Follow ESLint configuration
- Use Prettier for code formatting
- Write meaningful commit messages
- Add JSDoc comments for functions
- Maintain test coverage above 80%

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Express.js](https://expressjs.com/) - Fast, unopinionated, minimalist web framework
- [React](https://reactjs.org/) - A JavaScript library for building user interfaces
- [MongoDB](https://www.mongodb.com/) - The database for modern applications
- [Tailwind CSS](https://tailwindcss.com/) - A utility-first CSS framework


### Reporting Issues
When reporting issues, please include:
- Operating system and version
- Node.js version
- Steps to reproduce
- Expected vs actual behavior
- Screenshots (if applicable)

---

## 🚀 Quick Start Checklist

- [ ] Clone repository
- [ ] Install dependencies (backend & frontend)
- [ ] Setup MongoDB
- [ ] Configure environment variables
- [ ] Start backend server
- [ ] Start frontend development server
- [ ] Create first employee
- [ ] Test leave application flow
- [ ] Test approval workflow


---

*Made with ❤️ for efficient leave management*
