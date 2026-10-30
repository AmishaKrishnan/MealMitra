#  MealMitra – Food Donation Management Platform

MealMitra is a web-based food donation management platform developed to reduce food wastage by connecting food donors with NGOs. It provides a centralized platform where donors can share surplus food, NGOs can discover and accept suitable donations, and administrators can monitor platform activities.

The main objective of MealMitra is to make food donation and collection easier, faster, and more organized.

##  Features

###  Donor Module
- User registration and login.
- Create food donation listings.
- Add food name, type, dietary preference, quantity, servings, and description.
- Provide food pickup address and location.
- View and track submitted donations.
- Monitor donation status.
- Cancel eligible pending donations.

###  NGO Module
- NGO registration and login.
- View available food donations.
- Manage supported food types and dietary preferences.
- View donation recommendations.
- Accept suitable donations.
- Manage accepted donations and collection activities.
- Update donation status during pickup and completion.
- View donor pickup locations using Google Maps.
- Access an NGO support assistant powered by the Gemini API.

###  Admin Module
- Access the admin dashboard.
- Monitor users and donations.
- View dashboard statistics.
- Manage platform records and activities.

###  Map Integration
- Leaflet is used on the donation creation page to select pickup locations.
- Google Maps embedding is used in the NGO dashboard to display donor locations.
- Latitude and longitude coordinates are stored with donation information.

##  Technology Stack

| Component | Technology |
|---|---|
| Frontend | Angular 22 |
| Frontend Language | TypeScript |
| Backend | Node.js |
| Backend Framework | Express.js |
| Database | MongoDB |
| ODM | Mongoose |
| Authentication | JSON Web Token (JWT) |
| Password Security | bcryptjs |
| Maps | Leaflet and Google Maps Embed |
| Support Assistant | Google Gemini API |
| Package Manager | npm |

##  System Architecture

MealMitra follows a client-server architecture.

1. **Frontend:** Angular provides the user interface for donors, NGOs, and administrators.
2. **Backend:** Node.js and Express.js handle API requests, authentication, validation, and application logic.
3. **Database:** MongoDB stores user details, donation information, and related records.
4. **Map Integration:** Leaflet and Google Maps embedding provide location-related functionality.
5. **Support Assistant:** The Gemini API powers the NGO support assistant.

## 🔄 Application Workflow

1. Users register and log in to the platform.
2. Donors submit food donation details.
3. The backend validates the information and stores the donation in MongoDB.
4. NGOs view available donations.
5. NGOs accept suitable donations.
6. The backend updates the donation status.
7. NGOs manage pickup and completion of accepted donations.
8. Users can track donation progress through the platform.

##  Project Structure

```text
MealMitra/
│
├── frontend/
│   ├── src/
│   ├── angular.json
│   └── package.json
│
├── backend/
│   ├── src/
│   │   ├── config/
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── models/
│   │   ├── routes/
│   │   └── services/
│   ├── server.js
│   └── package.json
│
├── .gitignore
└── README.md
```

## ⚙️ Prerequisites

Before running the project, install:

- Node.js
- npm
- Angular CLI
- MongoDB
- Git

##  Installation and Setup

### 1. Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd MealMitra
```

### 2. Backend Setup

Open a terminal and navigate to the backend folder:

```bash
cd backend
npm install
```

Create a `.env` file inside the backend folder and configure the required environment variables:

```env
MONGODB_URI=mongodb://127.0.0.1:27017/mealmitra
PORT=5000
JWT_SECRET=your_secure_secret_key
GEMINI_API_KEY=your_gemini_api_key
```

Start MongoDB before running the backend.

Run the backend:

```bash
npm run dev
```

Alternatively:

```bash
npm start
```

Backend URL:

```text
http://localhost:5000
```

Health check:

```text
http://localhost:5000/api/health
```

### 3. Frontend Setup

Open a second terminal:

```bash
cd frontend
npm install
```

Start the Angular application:

```bash
npm start
```

Alternatively:

```bash
npx ng serve
```

Frontend URL:

```text
http://localhost:4200
```

## 🔌 Backend API Overview

The backend provides REST API endpoints for communication between the frontend and database.

| API Route | Purpose |
|---|---|
| `/api/auth` | User registration and login |
| `/api/users` | User profile and preferences |
| `/api/donations` | Donation management |
| `/api/admin` | Administrative operations |
| `/api/public/stats` | Public platform statistics |
| `/api/support` | NGO support assistant |
| `/api/health` | Backend health check |

### Donation Operations

| Method | Endpoint | Purpose |
|---|---|---|
| POST | `/api/donations` | Create a donation |
| GET | `/api/donations/my` | View personal donations |
| GET | `/api/donations/available` | View available donations |
| GET | `/api/donations/accepted` | View accepted donations |
| GET | `/api/donations/:id` | View a specific donation |
| PATCH | `/api/donations/:id/accept` | Accept a donation |
| PATCH | `/api/donations/:id/pickup` | Update pickup status |
| PATCH | `/api/donations/:id/complete` | Complete a donation |
| PATCH | `/api/donations/:id/cancel` | Cancel a donation |

##  Database

MealMitra uses MongoDB to store application information.

The main data models include:

- **User:** Stores donor and NGO account information, profile details, and preferences.
- **Donation:** Stores food details, quantity, pickup information, coordinates, donation status, and acceptance information.

##  Security

The backend includes:

- JWT-based authentication.
- Password hashing using bcryptjs.
- Authentication middleware.
- Role-based access control.
- Backend-side validation and authorization.


##  Future Enhancements

- Improved donor and NGO matching.
- Real-time notifications.
- Location-based donation recommendations.
- Collection route optimization.
- Donation analytics and reporting.
- Improved deployment and scalability.

##  Project Objective

MealMitra aims to bridge the gap between surplus food and people in need by connecting donors and NGOs through a digital platform. It encourages food sharing, reduces wastage, and makes donation management more efficient.

##  Contributors

Developed as an academic group project by MCA students at **St. Aloysius (Deemed to be University), Mangaluru**.

##  License

This project is developed for academic and educational purposes. No open-source license has been specified yet.