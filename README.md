# Blog Platform

A full-stack blog platform built with Node.js (Express) for the backend and React for the frontend. This project allows users to register, log in, create stories, comment, upload images, and manage their profiles. It is designed for scalability, security, and ease of use.

---

## Table of Contents
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Setup Instructions](#setup-instructions)
- [API Endpoints](#api-endpoints)
- [Frontend Overview](#frontend-overview)
- [Backend Overview](#backend-overview)
- [Environment Variables](#environment-variables)
- [Contributing](#contributing)
- [License](#license)

---

## Features
- User authentication (register, login, JWT-based sessions)
- Create, edit, delete stories (blog posts)
- Comment on stories
- Upload images for stories and user profiles
- Email notifications
- Error handling and custom error responses
- RESTful API design
- Responsive frontend UI

---

## Tech Stack
- **Backend:** Node.js, Express.js
- **Frontend:** React.js
- **Database:** MongoDB (assumed, can be changed)
- **Authentication:** JWT
- **Image Uploads:** Multer, local storage
- **Email:** Nodemailer

---

## Project Structure
```
Backend/
  Controllers/        # Route logic for auth, comment, story, user
  Helpers/            # Utility functions (token, database, error, input, image, email)
  Middlewares/        # Auth, error handling, database error handler
  Models/             # Mongoose models for user, story, comment
  Routers/            # Express routers for API endpoints
  public/             # Static files (story images, user photos)
  server.js           # Entry point for backend server
Frontend/
  public/             # Static assets
  src/                # React source code
    components/       # Reusable UI components
    Context/          # React context providers
    Css/              # Stylesheets
    App.js            # Main React app
    index.js          # Entry point
```

---

## Setup Instructions

### Prerequisites
- Node.js (v16+ recommended)
- npm or yarn
- MongoDB (local or cloud)

### Backend Setup
1. Navigate to the `Backend` folder:
   ```cmd
   cd Backend
   ```
2. Install dependencies:
   ```cmd
   npm install
   ```
3. Create a `.env` file in `Backend/` with the following variables:
   ```env
   PORT=5000
   MONGODB_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret
   EMAIL_USER=your_email@example.com
   EMAIL_PASS=your_email_password
   ```
4. Start the backend server:
   ```cmd
   npm start
   ```

### Frontend Setup
1. Navigate to the `Frontend` folder:
   ```cmd
   cd Frontend
   ```
2. Install dependencies:
   ```cmd
   npm install
   ```
3. Start the frontend development server:
   ```cmd
   npm start
   ```

---

## API Endpoints

### Auth
- `POST /api/auth/register` — Register a new user
- `POST /api/auth/login` — Login and receive JWT
- `GET /api/auth/profile` — Get user profile (protected)

### Stories
- `GET /api/story` — List all stories
- `POST /api/story` — Create a new story (protected)
- `PUT /api/story/:id` — Edit a story (protected)
- `DELETE /api/story/:id` — Delete a story (protected)

### Comments
- `POST /api/comment` — Add a comment to a story (protected)
- `GET /api/comment/:storyId` — Get comments for a story

### Users
- `GET /api/user/:id` — Get user details
- `PUT /api/user/:id` — Update user profile (protected)

### Image Uploads
- `POST /api/story/upload-image` — Upload story image
- `POST /api/user/upload-photo` — Upload user profile photo

---

## Frontend Overview
- Built with React.js
- Uses Context API for state management
- Responsive design with custom CSS
- Components for login, registration, story list, story details, comments, profile management
- API calls handled via Axios or Fetch

---

## Backend Overview
- Express.js REST API
- Controllers for business logic
- Middlewares for authentication, error handling
- Mongoose models for MongoDB data
- Helpers for token management, input validation, image upload, email sending

---

## Environment Variables
- `PORT`: Port for backend server
- `MONGODB_URI`: MongoDB connection string
- `JWT_SECRET`: Secret for JWT authentication
- `EMAIL_USER`: Email address for sending notifications
- `EMAIL_PASS`: Email password or app password

---

## Contributing
1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes
4. Push to your branch (`git push origin feature/your-feature`)
5. Open a pull request
