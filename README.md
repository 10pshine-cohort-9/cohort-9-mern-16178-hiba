# cohort-9-mern-16178-hiba

Cohort 9 — MERN (NodeJS+ReactJS) assignment for Hiba Saud Anwari

# Leaflet Notes App

A full-stack notes management application built with **React.js** and **Node.js**, providing secure authentication, personal note management, rich-text editing, search and sorting, trash and recovery functionality, import/export capabilities, application logging, centralized error handling, automated testing and SonarQube-based code-quality analysis.

The application is designed with a focus on **security, maintainability, accessibility, reliability and a clean user experience**.

Users can:

- Create and edit notes
- Format notes using a rich text editor
- Pin and unpin important notes
- Search and sort notes
- Move notes to trash
- Restore deleted notes
- Permanently delete notes
- Import notes
- Export notes
- Manage their profile
- Reset their password
- Check password strength during registration
- Receive feedback through toast notifications
- Use the application across different screen sizes

The application also includes backend logging, centralized exception handling, authentication middleware, automated testing and SonarQube code-quality analysis.

# Key Features

## 1. User Authentication & Authorization

The application provides a complete authentication flow for users.

- User registration
- User login
- User logout
- Protected routes
- Cookie-based authentication
- Authentication middleware
- Forgot-password functionality
- Password reset functionality
- Form validation
- Authentication error handling
- Session/current-user handling
- User-specific notes

Each authenticated user notes are associated with their account, ensuring that users can only access and manage their own notes.

## 2. Password Strength Validation

The signup process includes password-strength analysis using the **zxcvbn** password-strength library.

- Password strength evaluation
- Real-time password feedback
- Minimum and maximum password length validation
- Confirmation-password validation
- Strong-password requirements
- Password visibility toggle
- Asynchronous password-strength checking
- User-friendly validation messages

This provides users with immediate feedback when creating a password and encourages stronger credentials.

## 3. Note Management

The core functionality of the application is complete note management.

Users can:

- Create new notes
- View notes
- Edit existing notes
- Save changes
- Delete notes
- Restore deleted notes
- Permanently delete notes
- Pin and unpin notes

Notes support rich content editing, allowing users to create more structured and readable notes.

## 4. Rich Text Editing

The application uses a rich-text editor to provide a better note-writing experience. Users can create formatted content rather than being limited to plain text.

This allows notes to contain structured and formatted information while providing a more user-friendly editing experience.

## 5. Pin & Unpin Notes

Users can :

- Pin notes
- Unpin notes
- Display pinned notes prominently
- Sort notes by pinned status
- Maintain pinned state while using other sorting options

The sorting logic also ensures that pinned notes are handled correctly when other sorting methods are selected.

## 6. Trash & Note Recovery

Deleted notes are moved to a trash area instead of being immediately removed permanently.
Users can :

- Move notes to trash
- View trashed notes
- Restore notes
- Permanently delete notes

This provides users with a recovery mechanism and prevents accidental deletion from immediately becoming permanent.

## 7. Search & Note Preview

The application provides note searching functionality.
Users can search through their notes and quickly identify relevant content.
Users can :

- Search notes
- Display matching notes
- Show note previews
- Handle empty search results
- Maintain a clean search experience

## 8. Sorting & Filtering

Notes can be organized using different sorting options.

- Sort by date
- Sort by title
- Sort by pinned status
- Ascending order
- Descending order
- Pin-first behavior where appropriate
- Fallback between `editedAt` and `createdAt`

The sorting logic was implemented carefully to ensure that changing the sorting method does not produce unexpected ordering.

## 9. Import Notes

The application supports importing notes from external files.

- TXT
- Multiple TXT files

The import functionality includes validation and error handling for invalid or unsupported files.

### Import handling includes

- JSON validation
- Unsupported-file handling
- Empty-file handling
- Multiple-file imports
- Import failure handling
- User feedback for import errors

## 10. Export Notes

Users can export their notes for external use or backup purposes.
The application supports exporting individual or multiple notes where applicable.
Export functionality also includes appropriate handling of export states and errors.

## 11. User Profile Management

Users can manage their profile information through the application.

### Profile functionality includes

- View profile information
- Update username
- Update email
- Update profile information
- Update profile-related data
- Handle profile update errors

# Backend

The backend is built using **Node.js** and **Express.js**.

It provides APIs for authentication, user management, notes, and other application functionality.

### Backend responsibilities include

- Authentication
- Authorization
- User management
- Note CRUD operations
- Profile management
- Database communication
- Request handling
- Validation
- Error handling
- Logging

# Database

The application uses **MySQL** as its relational database.
Database operations are handled using **Prisma ORM**.

### Database responsibilities

The database stores information such as:

- Users
- Notes
- Authentication-related information
- Note timestamps
- Note status
- Pinned state
- Other related application data

Prisma provides a structured and type-safe approach to communicating with the database.

# Prisma ORM

The backend uses **Prisma** for database access and schema management.

### Prisma is used for

- Database schema definition
- Database queries
- CRUD operations
- Migrations
- Relational data management
- Communication between the Express backend and MySQL

# Application Logging

The application uses **Pino Logger** for structured application logging.
Logging is implemented throughout the backend to make application behavior easier to monitor and debug.

### Logged information includes

- HTTP requests
- HTTP responses
- Important application events
- Errors
- Exceptions
- Backend operations
- Relevant user activities

Structured logging makes it easier to diagnose issues and understand application behavior.

# Exception & Error Handling

The backend implements centralized exception handling through Express middleware.
Instead of handling every error independently, errors are passed through centralized error-handling logic.

### Error handling includes

- Global exception handling
- Centralized error middleware
- Meaningful API error responses
- HTTP status handling
- Validation errors
- Authentication errors
- Database/API errors
- Unexpected server errors
- Pino logging for exceptions

This improves reliability and ensures that errors are handled consistently throughout the application.

# Authentication Middleware

Protected backend routes use authentication middleware to verify the user's authenticated session.

The middleware is responsible for:

- Reading authentication information
- Verifying authentication
- Protecting private routes
- Preventing unauthorized access
- Making authenticated user information available to protected operations

# API Communication

The frontend communicates with the backend through a reusable API utility.
A centralized `apiFetch` utility is used to handle API requests consistently.
This provides a cleaner communication layer between the React frontend and Express backend.

# Frontend

The frontend is built using **React.js** with **Vite**.
It provides an interactive and responsive user interface for authentication, note management, profile management, search, sorting, importing, exporting, and other application functionality.

### Frontend includes

- Reusable React components
- React Context
- React Router
- Form handling
- Validation
- API communication
- Toast notifications
- Loading states
- Error states
- Responsive layouts
- Accessibility improvements
- Rich-text editing

# UI & User Experience

The application uses **Tailwind CSS** to create a clean and responsive interface.
UI features include :

- Responsive layouts
- Reusable components
- Interactive buttons
- Toast notifications
- Loading indicators
- Empty states
- Error states
- Password visibility controls
- Search interface
- Sorting controls
- Import/export controls
- Modal interactions
- Accessible form controls
- Consistent icons and visual feedback

# Accessibility

Accessibility considerations were included throughout the frontend.
Examples include:

- Proper form labels
- Accessible buttons
- `aria-label`
- `aria-invalid`
- `aria-describedby`
- Semantic HTML
- Accessible error messages
- Keyboard-friendly controls
- Clear validation feedback
  Accessibility-related code-quality issues identified during analysis were also reviewed and improved.

# Notifications & User Feedback

The application provides feedback to users through toast notifications and UI states.
Feedback is provided for actions such as:

- Successful account creation
- Successful note operations
- Errors
- Import failures
- Export states
- Validation problems
- Other important application events
  This makes application behavior clear to the user instead of silently performing operations.

# Testing

Automated testing was implemented for both frontend and backend functionality.

## Frontend Testing

The frontend uses **Jest** together with **React Testing Library**.
Tests cover important components, contexts, and user interactions.
Testing includes areas such as:

- Login
- Signup
- Forgot password
- Reset password
- Note management
- Notes context
- Note cards
- Note action controls
- Profile Context
- Import functionality
- Export functionality
- Form validation
- Error handling
- Theme Context

The tests verify both expected behavior and important edge cases.

## Backend Testing

Backend functionality is covered through automated unit testing.
Tests target important backend logic such as:

- Controllers
- Services
- Authentication
- Note operations
- Validation
- Error handling
- Data access behavior
  The project follows the assignment's backend testing requirements and uses the appropriate testing tools configured for the backend.

# SonarQube & Code Quality

**SonarQube** was integrated into the project to analyze source-code quality and identify potential issues.
The analysis was used to identify and improve areas such as:

- Bugs
- Code smells
- Reliability
- Maintainability
- Cognitive complexity
- Duplicated or unnecessary logic
- Accessibility issues
- Code structure
- Error handling
- General code quality
  After running SonarQube analysis, the identified issues were reviewed and the relevant code was refactored or improved.

A `sonar-project.properties` configuration file is included in the project to support SonarQube analysis.

# Code Quality Improvements

Several improvements were made as part of the quality-improvement phase.
These include:

- Refactoring complex functions
- Reducing cognitive complexity
- Improving component structure
- Extracting reusable logic
- Improving error handling
- Improving accessibility
- Cleaning up unnecessary code
- Improving state management
- Improving sorting behavior
- Handling edge cases
- Improving test coverage
- Fixing issues identified during static analysis

The goal was not only to make the application functional but also to make the code easier to maintain and extend.

# Technology Stack

## Frontend

- **React.js**
- **Vite**
- **JavaScript**
- **Tailwind CSS**
- **React Router**
- **React Context API**
- **ReactQuill**
- **React Testing Library**
- **zxcvbn**
- **canvas-confetti**

## Backend

- **Node.js**
- **Express.js**
- **Prisma ORM**
- **MySQL**
- **Pino Logger**
- **Authentication Middleware**
- **Centralized Error Handling**

## Testing & Quality

- **Jest**
- **React Testing Library**
- **Mocha/Chai where configured for backend testing**
- **SonarQube**
- **SonarScanner**

## Development & Version Control

- **Git**
- **GitHub**
- **VS Code**
- **npm**

# Git & Version Control

Git is used throughout development to manage source code and feature development.
The project uses feature-based branching to keep different areas of development organized.

Git was also used for:

- Feature development
- Bug fixes
- Refactoring
- Testing work
- Code-quality improvements
- Merging changes
- Rebase and branch management
- Pull requests
- Code review

# Engineering Practices

The project follows several software-development practices, including:

- Component-based React architecture
- Separation of frontend and backend responsibilities
- Reusable components and utilities
- Centralized state management
- API abstraction
- Middleware-based backend architecture
- Centralized exception handling
- Structured logging
- Automated testing
- Static code analysis
- Accessibility considerations
- Input validation
- Error handling
- Edge-case handling
- Maintainable code structure
- Git-based version control

# Additional Implementations

In addition to the core assignment requirements, the application includes several additional features and improvements:

- Password-strength analysis using `zxcvbn`
- Password visibility controls
- Rich-text note editing
- Pin/unpin functionality
- Trash and note recovery
- Permanent deletion
- Search with note previews
- Multiple sorting options
- Ascending and descending sorting
- TXT import
- Multiple TXT file import
- Note export functionality
- Toast notifications
- Loading and submission states
- Responsive UI
- React Context-based state management
- Reusable UI components
- Accessibility improvements
- Form validation
- Centralized API communication
- Structured backend logging
- Centralized exception handling
- SonarQube-based code-quality improvements
- Automated frontend and backend testing
- Handling of invalid files and edge cases

# Project Status

**Status: Completed**

The application includes the required full-stack technologies and core functionality, along with additional features for usability, reliability, testing, accessibility and code quality.
The project has also undergone automated testing and SonarQube analysis, with identified code-quality issues reviewed and addressed through refactoring and improvements.
