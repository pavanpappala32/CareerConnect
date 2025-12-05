📌 CareerConnect — Job Portal Web Application

A MERN-stack platform that connects job seekers with employers in a smooth, efficient, and secure way.

🚀 Overview

CareerConnect is a full-stack job portal developed using the MERN stack (MongoDB, Express, React, Node.js).
It allows users to:

Create accounts (job seeker or recruiter)

Apply for jobs

Manage applications

Post and manage job listings

Track job application status

Authenticate securely using JWT

This project demonstrates clean backend architecture, MVC structure, modular routing, middleware-based processing, and proper error handling.

⭐ Key Features
👨‍💼 For Job Seekers

Browse available job listings

Apply for jobs

Track application status

Secure login & profile management

🏢 For Recruiters

Post new job openings

Edit or delete job posts

Manage applications submitted to their job listings

🔐 Security & Backend Architecture

JWT authentication (login-protected routes)

Error handling middleware

Reusable controllers & services

Environment variable support (.env)

🏗️ Tech Stack
Layer	Technology
Frontend	React (not included fully in this zip)
Backend	Node.js, Express.js
Database	MongoDB
Auth	JWT, bcrypt
Architecture	MVC Pattern
📂 Project Structure (Backend)
CareerConnect/
├── backend/
│   ├── controllers/
│   │   ├── applicationController.js
│   │   ├── jobController.js
│   │   └── userController.js
│   │
│   ├── database/
│   │   └── dbConnection.js
│   │
│   ├── middlewares/
│   │   ├── auth.js
│   │   ├── catchAsyncError.js
│   │   └── error.js
│   │
│   ├── models/
│   │   ├── applicationSchema.js
│   │   ├── jobSchema.js
│   │   └── userSchema.js
│   │
│   ├── routes/
│   │   ├── applications.js
│   │   ├── jobs.js
│   │   └── users.js
│   │
│   ├── utils/
│   │   └── errorHandler.js
│   │
│   ├── app.js
│   ├── server.js
│   ├── package.json
│   ├── package-lock.json
│   └── .env

📘 Explanation of Important Folders
1️⃣ controllers/

Contains the business logic for each module.

userController → Signup, login, authentication

jobController → Create job, get jobs, update job

applicationController → Apply for job, track application

2️⃣ models/

Defines MongoDB Schemas using Mongoose.

userSchema → name, email, role, hashed password

jobSchema → job title, company, description, postedBy

applicationSchema → applicantId, jobId, status

3️⃣ middlewares/

auth.js → Protect routes using JWT

error.js → Handles all errors in one place

catchAsyncError.js → Wraps async controllers to avoid try/catch repetition

4️⃣ routes/

Maps APIs to controller functions.

For example:

Route File	Purpose
users.js	Signup, login, profile
jobs.js	Job CRUD operations
applications.js	Applying & viewing applications
5️⃣ dbConnection.js

Manages MongoDB connection.

6️⃣ server.js & app.js

app.js → Configures middleware, routes

server.js → Starts server & connects to DB

⚙️ Installation & Setup Guide
1️⃣ Clone the repository
git clone <repo-url>
cd CareerConnect/backend

2️⃣ Install dependencies
npm install

3️⃣ Configure .env file

Create .env inside /backend:

PORT=4000
MONGO_URI=mongodb://127.0.0.1:27017/careerconnect
JWT_SECRET=mysecret
JWT_EXPIRE=5d

4️⃣ Start the server
npm start


Server will run on:

http://localhost:4000

🔌 API Endpoints Overview
👤 User Authentication
Method	Endpoint	Description
POST	/api/v1/user/register	Register user
POST	/api/v1/user/login	Login user
GET	/api/v1/user/profile	Get logged-in user
💼 Jobs API
Method	Endpoint	Description
POST	/api/v1/job/create	Create job (recruiter only)
GET	/api/v1/job/all	Get all jobs
GET	/api/v1/job/:id	Get job details
PUT	/api/v1/job/:id	Update job
DELETE	/api/v1/job/:id	Delete job
📨 Applications API
Method	Endpoint	Description
POST	/api/v1/application/apply/:jobId	Apply for job
GET	/api/v1/application/my-applications	Get user’s applications
GET	/api/v1/application/job/:jobId	Recruiter view of applicants
🧠 How Authentication Works

User logs in → server generates a JWT token

Token is stored in cookies / localstorage (frontend)

Protected routes use auth.js middleware to:

Verify token

Attach user to req.user

Allow access only to authenticated users

🚧 Future Enhancements

Resume upload system

Admin dashboard

Job recommendation engine (ML-based)

Email notifications for application updates

Complete React frontend integration

🤝 Contributing

Pull requests are welcome!
Follow branching pattern:

feature/<feature-name>
fix/<bug-name>

📄 License

This project is licensed under MIT License.

