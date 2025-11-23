# Audit Tracker - Enterprise Audit Management System

<div align="center">

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-ISC-green.svg)
![Node](https://img.shields.io/badge/node-18.x-brightgreen.svg)
![Next.js](https://img.shields.io/badge/next.js-15.5.4-black.svg)

**A comprehensive, full-stack audit management system for tracking programs, schedules, audit sessions, observations, problems, corrective actions, and approvals.**

[🌐 Live Demo](https://audit-management-chi.vercel.app/) • [📱 Frontend Repo](https://github.com/Rakibulislam-emon/Audit_tracker_frontend) • [⚙️ Backend Repo](https://github.com/Rakibulislam-emon/Audit_tracker_backend) • [Features](#-features) • [Tech Stack](#-technology-stack) • [Installation](#-installation)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Technology Stack](#-technology-stack)
- [Architecture](#-architecture)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Project Structure](#-project-structure)
- [API Documentation](#-api-documentation)
- [Usage Guide](#-usage-guide)
- [Development](#-development)
- [Dark Mode](#-dark-mode-support)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

---

## 🎯 Overview

**Audit Tracker** is an enterprise-grade audit management system designed to streamline the entire audit lifecycle from planning to approval. The system provides a centralized platform for managing audit programs, scheduling sessions, recording observations, tracking problems, implementing corrective actions, and managing approval workflows.

### Key Capabilities

- **Complete Audit Lifecycle Management**: From program creation to final report approval
- **Role-Based Access Control**: Secure multi-role system (Admin, Audit Manager, Auditor, Compliance Officer, SysAdmin)
- **Dynamic Universal Components**: Reusable CRUD components that auto-generate forms, tables, and filters
- **Approval Workflow System**: Comprehensive approval management with requirements validation
- **Real-time Data Management**: Seamless data synchronization using React Query
- **Professional UI/UX**: Modern, responsive design with full dark mode support
- **File Management**: Cloudinary integration for proof documents and images

---

## ✨ Features

### Core Functionality

#### 📊 Audit Management

- **Program Management**: Create and manage audit programs with status tracking
- **Schedule Management**: Plan and schedule audit sessions with automatic session creation
- **Audit Sessions**: Central "Mission Control" dashboard for each audit session
- **Template System**: Reusable audit templates with customizable questions
- **Question Management**: Dynamic question types (Yes/No, Text, Number, Rating, Dropdown)

#### 🔍 Observations & Findings

- **Observation Recording**: Real-time observation capture during audit sessions
- **Problem Tracking**: Log and categorize problems with severity levels
- **Fix Actions**: Create and track corrective actions with verification
- **Proof Management**: Upload and manage supporting documents/images
- **Severity Classification**: Informational, Low, Medium, High, Critical

#### 📝 Reporting & Approval

- **Report Generation**: Auto-generate comprehensive audit reports
- **Approval Workflow**: Multi-level approval system with requirements validation
- **Status Tracking**: Real-time status updates across all entities
- **Comments System**: Approval/rejection comments for audit trail
- **My Approvals**: Personal approval queue for each user

#### 👥 Organization Management

- **Company Management**: Multi-company support
- **Site Management**: Track multiple sites per company
- **Team Management**: Assign teams to audit sessions
- **Group Management**: Organize users into groups
- **User Management**: Complete user lifecycle management

#### 🎨 User Experience

- **Universal CRUD System**: Auto-generated forms, tables, and filters
- **Advanced Filtering**: Multi-criteria search and filter capabilities
- **Responsive Design**: Mobile, tablet, and desktop optimized
- **Dark Mode**: Full dark/light theme support with automatic status color adaptation
- **Real-time Updates**: Seamless data refresh without page reloads
- **Interactive UI**: Smooth animations and transitions

### Security Features

- **JWT Authentication**: Secure token-based authentication
- **Role-Based Authorization**: Granular permission system
- **Password Hashing**: bcryptjs for secure password storage
- **CORS Protection**: Configurable cross-origin resource sharing
- **Input Validation**: Express-validator for request validation
- **Helmet Security**: HTTP header security middleware

---

## 🛠 Technology Stack

### Frontend

| Technology                | Version  | Purpose                         |
| ------------------------- | -------- | ------------------------------- |
| **Next.js**               | 15.5.4   | React framework with App Router |
| **React**                 | 19.1.0   | UI library                      |
| **TypeScript/JavaScript** | -        | Programming language            |
| **Tailwind CSS**          | 4.x      | Utility-first CSS framework     |
| **ShadCN/UI**             | Latest   | Component library               |
| **React Hook Form**       | 7.64.0   | Form management                 |
| **Zustand**               | 5.0.8    | State management                |
| **TanStack Query**        | 5.90.2   | Server state management         |
| **TanStack Table**        | 8.21.3   | Data table component            |
| **Framer Motion**         | 12.23.22 | Animation library               |
| **Next Themes**           | 0.4.6    | Theme management                |
| **Axios**                 | 1.12.2   | HTTP client                     |
| **Lucide React**          | 0.544.0  | Icon library                    |
| **Sonner**                | 2.0.7    | Toast notifications             |
| **Zod**                   | 4.1.12   | Schema validation               |

### Backend

| Technology            | Version | Purpose                       |
| --------------------- | ------- | ----------------------------- |
| **Node.js**           | 18.x    | Runtime environment           |
| **Express**           | 5.1.0   | Web framework                 |
| **MongoDB**           | Latest  | Database                      |
| **Mongoose**          | 8.18.2  | ODM for MongoDB               |
| **JWT**               | 9.0.2   | Authentication tokens         |
| **bcryptjs**          | 3.0.2   | Password hashing              |
| **Cloudinary**        | 1.41.3  | File upload service           |
| **Multer**            | 2.0.2   | File upload middleware        |
| **Express Validator** | 7.2.1   | Input validation              |
| **Helmet**            | 8.1.0   | Security middleware           |
| **CORS**              | 2.8.5   | Cross-origin resource sharing |
| **Morgan**            | 1.10.1  | HTTP request logger           |

---

## 🏗 Architecture

### System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                        Frontend (Next.js)                    │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │   Pages      │  │  Components  │  │   Services   │      │
│  │  (App Router)│  │  (Universal) │  │  (API Calls) │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
│         │                  │                  │             │
│         └──────────────────┼──────────────────┘             │
│                            │                                 │
│                    ┌───────▼────────┐                        │
│                    │State Management│                        │
│                    │ (Zustand/Query)│                        │
│                    └───────┬────────┘                        │
└────────────────────────────┼────────────────────────────────┘
                              │
                              │ REST API
                              │
┌─────────────────────────────▼────────────────────────────────┐
│                    Backend (Express)                          │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │   Routes     │  │ Controllers  │  │  Middleware   │      │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘      │
│         │                 │                  │             │
│         └─────────────────┼──────────────────┘             │
│                           │                                 │
│                    ┌──────▼────────┐                        │
│                    │    Models     │                        │
│                    │   (Mongoose)  │                        │
│                    └──────┬────────┘                        │
└────────────────────────────┼────────────────────────────────┘
                              │
                              │
                    ┌─────────▼─────────┐
                    │   MongoDB Atlas   │
                    │   Cloudinary      │
                    └───────────────────┘
```

### Data Flow

1. **User Action** → Frontend component
2. **State Update** → Zustand store or React Query
3. **API Call** → Service layer (Axios)
4. **Request** → Express route
5. **Validation** → Middleware (auth, validation)
6. **Business Logic** → Controller
7. **Data Access** → Model (Mongoose)
8. **Response** → Database/Cloudinary
9. **Update UI** → React Query invalidation

### Universal Component System

The system uses a revolutionary **Universal CRUD** architecture:

- **Single Configuration File**: `dynamicConfig.js` defines all modules
- **Auto-Generated Forms**: Forms generated from configuration
- **Auto-Generated Tables**: Tables with sorting, filtering, pagination
- **Auto-Generated Filters**: Dynamic filter components
- **Relation Management**: Automatic handling of relationships
- **Permission System**: Role-based access built-in

---

## 🚀 Installation

### Prerequisites

- **Node.js** 18.x or higher
- **MongoDB** instance (local or Atlas)
- **Cloudinary** account (for file uploads)
- **npm** or **yarn** package manager

### Step 1: Clone the Repositories

This is a monorepo structure. You'll need to clone both frontend and backend repositories:

```bash
# Clone Frontend Repository
git clone https://github.com/Rakibulislam-emon/Audit_tracker_frontend.git audit-frontend
cd audit-frontend

# Clone Backend Repository (in a separate directory)
cd ..
git clone https://github.com/Rakibulislam-emon/Audit_tracker_backend.git audit-backend
cd audit-backend
```

**Or** if you prefer to work with both in a single directory:

```bash
# Create project directory
mkdir audit-tracker
cd audit-tracker

# Clone both repositories
git clone https://github.com/Rakibulislam-emon/Audit_tracker_frontend.git audit-frontend
git clone https://github.com/Rakibulislam-emon/Audit_tracker_backend.git audit-backend
```

### Step 2: Backend Setup

```bash
# Navigate to backend directory
cd audit-backend

# Install dependencies
npm install

# Create .env file
cp .env.example .env
```

### Step 3: Frontend Setup

```bash
# Navigate to frontend directory (from project root)
cd audit-frontend

# Install dependencies
npm install
```

### Step 4: Environment Configuration

#### Backend `.env` (audit-backend/.env)

```env
# Server Configuration
PORT=5000
NODE_ENV=development

# Database
MONGODB_URI=mongodb://localhost:27017/audit-tracker
# Or MongoDB Atlas:
# MONGODB_URI=

# JWT Configuration
JWT_SECRET=your_super_secret_jwt_key_here_min_32_chars

# Cloudinary Configuration
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

#### Frontend `.env.local` (audit-frontend/.env.local)

```env
# API Configuration
NEXT_PUBLIC_API_URL=http://localhost:5000/api
```

### Step 5: Start Development Servers

#### Terminal 1 - Backend

```bash
cd audit-backend
npm run dev
```

Backend will run on `http://localhost:5000`

#### Terminal 2 - Frontend

```bash
cd audit-frontend
npm run dev
```

Frontend will run on `http://localhost:3000`

### Step 6: Access the Application

1. Open `http://localhost:3000` in your browser
2. Login with default admin credentials (create via registration endpoint)
3. Start managing your audits!

---

## ⚙️ Configuration

### MongoDB Setup

#### Local MongoDB

1. Install MongoDB locally
2. Start MongoDB service
3. Update `MONGODB_URI` in `.env`

#### MongoDB Atlas (Cloud)

1. Create account at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create a cluster
3. Get connection string
4. Update `MONGODB_URI` in `.env`

### Cloudinary Setup

1. Create account at [Cloudinary](https://cloudinary.com)
2. Get your credentials from Dashboard
3. Update Cloudinary config in backend `.env`

### User Roles

The system supports the following roles:

- **admin**: Full system access, can approve any request
- **sysadmin**: System administrator with all permissions
- **audit_manager**: Can manage audits, teams, and reports
- **auditor**: Can create observations and problems
- **compliance_officer**: Can review and approve reports

---

## 📁 Project Structure

```
audit-tracker/
├── audit-backend/                 # Backend API
│   ├── src/
│   │   ├── config/                # Configuration files
│   │   │   ├── config.js          # App configuration
│   │   │   ├── db.js              # MongoDB connection
│   │   │   └── cloudinary.js     # Cloudinary setup
│   │   ├── controllers/           # Business logic
│   │   │   ├── userController.js
│   │   │   ├── auditSessionController.js
│   │   │   ├── observationController.js
│   │   │   ├── problemController.js
│   │   │   ├── fixActionController.js
│   │   │   ├── reportController.js
│   │   │   ├── approvalController.js
│   │   │   └── ... (20 controllers)
│   │   ├── models/                # Mongoose schemas
│   │   │   ├── User.js
│   │   │   ├── AuditSession.js
│   │   │   ├── Observation.js
│   │   │   ├── Problem.js
│   │   │   ├── FixAction.js
│   │   │   ├── Report.js
│   │   │   ├── Approval.js
│   │   │   └── ... (15 models)
│   │   ├── routes/                # API routes
│   │   │   ├── index.js           # Route aggregator
│   │   │   ├── userRoutes.js
│   │   │   ├── auditSessionRoutes.js
│   │   │   └── ... (20 route files)
│   │   ├── middleware/            # Express middleware
│   │   │   ├── auth.js            # JWT authentication
│   │   │   ├── authorizeRoles.js  # Role-based access
│   │   │   └── upload.js          # File upload handling
│   │   ├── utils/                 # Helper functions
│   │   │   ├── helper.js
│   │   │   ├── approvalResolver.js
│   │   │   └── reportStatusHelper.js
│   │   └── server.js              # Entry point
│   ├── package.json
│   └── README.md
│
├── audit-frontend/                # Frontend Application
│   ├── src/
│   │   ├── app/                   # Next.js App Router
│   │   │   ├── auth/              # Authentication pages
│   │   │   │   └── login/
│   │   │   ├── dashboard/         # Dashboard pages
│   │   │   │   └── [role]/        # Role-based routes
│   │   │   │       ├── auditsessions/
│   │   │   │       ├── observations/
│   │   │   │       ├── problems/
│   │   │   │       ├── reports/
│   │   │   │       └── ... (15+ modules)
│   │   │   ├── globals.css        # Global styles + dark mode
│   │   │   └── layout.js          # Root layout
│   │   ├── components/            # React components
│   │   │   ├── ui/                # UI components (ShadCN)
│   │   │   │   ├── dynamic/       # Universal components
│   │   │   │   │   ├── UniversalCRUDManager.jsx
│   │   │   │   │   ├── UniversalForm.jsx
│   │   │   │   │   ├── UniversalTable.jsx
│   │   │   │   │   ├── UniversalFilters.jsx
│   │   │   │   │   └── UniversalActions.jsx
│   │   │   │   ├── observation/   # Module-specific
│   │   │   │   ├── problem/
│   │   │   │   ├── fixAction/
│   │   │   │   └── ... (UI components)
│   │   │   ├── theme-provider.jsx
│   │   │   └── login/
│   │   ├── config/                # Configuration
│   │   │   └── dynamicConfig.js   # Universal config (3000+ lines)
│   │   ├── services/              # API services
│   │   │   ├── universalService.js
│   │   │   ├── approvalService.js
│   │   │   ├── reportService.js
│   │   │   └── proofService.js
│   │   ├── stores/                # State management
│   │   │   └── useAuthStore.js    # Zustand store
│   │   ├── hooks/                 # Custom hooks
│   │   │   └── useUniversal.js    # Universal data hook
│   │   ├── providers/             # Context providers
│   │   │   └── QueryProvider.js   # React Query setup
│   │   └── utils/                 # Utilities
│   │       ├── auth-client.js
│   │       └── auth-server.js
│   ├── public/                    # Static assets
│   ├── package.json
│   ├── next.config.mjs
│   ├── tailwind.config.js
│   └── DARK_MODE_GUIDE.md        # Dark mode documentation
│
├── Context.md                     # Project context
├── README.md                      # This file
└── .gitignore
```

---

## 📚 API Documentation

### Base URL

```
Development: http://localhost:5000/api
Production: https://your-api-domain.com/api
```

### Authentication

All protected endpoints require a JWT token in the Authorization header:

```
Authorization: Bearer <your_jwt_token>
```

### Core Endpoints

#### Authentication

```http
POST /api/users/register
POST /api/users/login
GET  /api/users/profile
PUT  /api/users/profile
```

#### Audit Sessions

```http
GET    /api/auditSessions          # List all sessions
GET    /api/auditSessions/:id      # Get session details
POST   /api/auditSessions          # Create new session
PUT    /api/auditSessions/:id      # Update session
DELETE /api/auditSessions/:id      # Delete session
```

#### Observations

```http
GET    /api/observations           # List observations
GET    /api/observations/:id       # Get observation
POST   /api/observations           # Create observation
PUT    /api/observations/:id       # Update observation
DELETE /api/observations/:id       # Delete observation
```

#### Problems

```http
GET    /api/problems               # List problems
GET    /api/problems/:id           # Get problem
POST   /api/problems               # Create problem
PUT    /api/problems/:id           # Update problem
DELETE /api/problems/:id           # Delete problem
```

#### Fix Actions

```http
GET    /api/fix-actions           # List fix actions
GET    /api/fix-actions/:id        # Get fix action
POST   /api/fix-actions            # Create fix action
PUT    /api/fix-actions/:id        # Update fix action
DELETE /api/fix-actions/:id         # Delete fix action
```

#### Reports

```http
GET    /api/reports                # List reports
GET    /api/reports/:id            # Get report
POST   /api/reports                # Create report
POST   /api/reports/generate       # Auto-generate report
POST   /api/reports/:id/submit     # Submit for approval
PUT    /api/reports/:id            # Update report
DELETE /api/reports/:id            # Delete report
```

#### Approvals

```http
GET    /api/approvals              # List approvals
GET    /api/approvals/my-approvals # User's approval queue
GET    /api/approvals/:id          # Get approval
POST   /api/approvals/:id/approve  # Approve request
POST   /api/approvals/:id/reject   # Reject request
PATCH  /api/approvals/:id/requirement # Update requirement
DELETE /api/approvals/:id          # Delete approval (admin)
```

#### Proofs (File Uploads)

```http
GET    /api/proofs                 # List proofs
POST   /api/proofs                 # Upload proof (multipart/form-data)
DELETE /api/proofs/:id              # Delete proof
```

### Complete API Reference

See [Backend README](https://github.com/Rakibulislam-emon/Audit_tracker_backend) for detailed API documentation.

---

## 📖 Usage Guide

### Creating an Audit Program

1. Navigate to **Programs** → **Create New**
2. Fill in program details (name, description, status)
3. Set program status (planning, in-progress, completed)
4. Save program

### Scheduling an Audit Session

1. Go to **Schedules** → **Create New**
2. Select program, template, and dates
3. Assign team members
4. Click **Start Schedule** to auto-create audit session

### Conducting an Audit

1. Open **Audit Sessions** → Select session
2. View **Mission Control** dashboard
3. Navigate to **Observations** tab
4. Answer questions and record observations
5. Create problems for non-conformances
6. Add fix actions for problems
7. Upload proof documents

### Generating Reports

1. Go to **Reports** → **Generate Report**
2. Select audit session
3. Choose report type (draft, preliminary, final, executive)
4. Review generated report
5. Submit for approval

### Approval Workflow

1. **Submit for Approval**: From report page
2. **Complete Requirements**: Check all requirement items
3. **Approve/Reject**: From "My Approvals" or approvals list
4. **Add Comments**: Optional for approval, required for rejection
5. **Status Updates**: Automatic propagation to related entities

### Universal Component Usage

The system uses a configuration-driven approach. To add a new module:

1. Add model in `audit-backend/src/models/`
2. Add controller in `audit-backend/src/controllers/`
3. Add routes in `audit-backend/src/routes/`
4. Add configuration in `audit-frontend/src/config/dynamicConfig.js`
5. Component automatically generates UI!

---

## 💻 Development

### Development Scripts

#### Backend

```bash
npm run dev      # Start with nodemon (auto-reload)
npm start        # Start production server
```

#### Frontend

```bash
npm run dev      # Start development server (Turbopack)
npm run build    # Build for production
npm start        # Start production server
npm run lint     # Run ESLint
```

### Code Style

- **ESLint**: Configured for Next.js
- **Prettier**: Recommended for code formatting
- **Conventions**: Follow existing code patterns

### Adding New Features

1. **Backend**: Add model → controller → routes
2. **Frontend**: Add config → component (if needed)
3. **Testing**: Test in both light and dark modes
4. **Documentation**: Update README if needed

### Universal Component System

The Universal CRUD system allows you to add new modules with minimal code:

```javascript
// In dynamicConfig.js
newModule: {
  endpoint: "new-module",
  title: "New Module",
  fields: {
    name: { type: "text", label: "Name", required: true },
    status: { type: "select", options: ["active", "inactive"] }
  },
  permissions: {
    create: ["admin"],
    edit: ["admin", "manager"],
    delete: ["admin"]
  }
}
```

That's it! Forms, tables, and filters are auto-generated.

---

## 🌙 Dark Mode Support

The application features comprehensive dark mode support with automatic theme adaptation. See [DARK_MODE_GUIDE.md](audit-frontend/DARK_MODE_GUIDE.md) for:

- Theme variable reference
- Component patterns
- Best practices
- Common pitfalls to avoid

### Key Features

- ✅ Automatic status badge color adaptation
- ✅ Theme-aware components
- ✅ Smooth theme transitions
- ✅ System preference detection
- ✅ Manual theme toggle

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature/amazing-feature`
3. **Make your changes**: Follow code style and add tests
4. **Commit changes**: `git commit -m 'Add amazing feature'`
5. **Push to branch**: `git push origin feature/amazing-feature`
6. **Open a Pull Request**: Describe your changes clearly

### Contribution Guidelines

- Follow existing code patterns
- Add comments for complex logic
- Test in both light and dark modes
- Update documentation if needed
- Ensure all tests pass

---

## 📄 License

This project is licensed under the **ISC License**.

---

## 🔗 Links

- **🌐 Live Demo**: [https://audit-management-chi.vercel.app/](https://audit-management-chi.vercel.app/)
- **📱 Frontend Repository**: [https://github.com/Rakibulislam-emon/Audit_tracker_frontend](https://github.com/Rakibulislam-emon/Audit_tracker_frontend)
- **⚙️ Backend Repository**: [https://github.com/Rakibulislam-emon/Audit_tracker_backend](https://github.com/Rakibulislam-emon/Audit_tracker_backend)

## 👥 Team

**Developed by**: Ninja-dev Team  
**Contact**: [rakibulislamemon@gmail.com](mailto:rakibulislamemon@gmail.com)

---

## 🎯 Roadmap

### Completed ✅

- ✅ Core audit management system
- ✅ Universal CRUD component system
- ✅ Approval workflow with requirements
- ✅ Report generation and submission
- ✅ Dark mode support
- ✅ File upload system
- ✅ Role-based access control

### In Progress 🚧

- 🚧 Approval notifications
- 🚧 Dashboard analytics
- 🚧 Advanced reporting features

### Planned 📋

- 📋 Email notifications
- 📋 Export to PDF/Excel
- 📋 Mobile app
- 📋 Advanced analytics dashboard
- 📋 Audit trail and history
- 📋 Bulk operations

---

## 🙏 Acknowledgments

- **ShadCN/UI** for the amazing component library
- **TanStack** for React Query and Table
- **Next.js** team for the excellent framework
- **MongoDB** for the robust database
- **Cloudinary** for file management

---

## 📞 Support

For support, email [rakibulislamemon@gmail.com](mailto:rakibulislamemon@gmail.com) or open an issue in the repository.

---

<div align="center">

**Built with ❤️ by the Audit Tracker Team**

⭐ Star this repo if you find it helpful!

</div>
