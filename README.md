*🎓 FAST Student Facilitator — Campus Services Platform
A full-stack campus services platform built with **React** on the frontend and **Spring Boot / Java** on the backend, powered by a **PostgreSQL** database. Designed to streamline everyday campus life for students through timetables, carpooling, lost & found, book exchange, and more.

Developed by:

* L24-3023 Muhammad Shehryar Waheed

🎮 Features

* 📝 Login & Google OAuth — Sign in to access personalized features
* 🗓️ Timetable Manager — Upload, parse, and manage class timetables (Excel/CSV)
* 🗺️ Campus Map — Search and navigate campus locations
* 🚗 Carpool — Offer and find rides with other students
* 📚 Past Papers — Browse and upload past exam papers
* 📦 Lost & Found — Post and search lost/found item listings
* 📖 Book Exchange — Buy, sell, or swap textbooks
* 📅 Campus Event Board — View upcoming campus events
* ⏰ Reminders — Create and track personal reminders
* 🛠️ Admin Panel — Moderate content and manage users
* 📊 Stats & Analytics — Visual reports and usage charts

🛠️ Prerequisites
Before running the app, make sure you have the following installed:

* [Java JDK](https://adoptium.net/) 17 or higher
* [Node.js](https://nodejs.org/) 18 or higher (with npm)
* [PostgreSQL](https://www.postgresql.org/download/) (running on port 5432)

🚀 How to Run Locally

Step 1 — Clone the Repository

```
git clone https://github.com/<your-org>/FAST-Student-Facilitator.git
```

Or download the ZIP directly from the green Code button above.

Step 2 — Database Configuration

1. Start the PostgreSQL service.
2. Create a database named:

```
fsf_db
```

3. Configure your own PostgreSQL username and password by either:
   * Creating `application-local.properties` inside the `backend` folder, or
   * Setting the following environment variables:

```
SPRING_DATASOURCE_USERNAME
SPRING_DATASOURCE_PASSWORD
```

Step 3 — Backend Setup & Run

1. Open a terminal and navigate to the backend directory:

```
cd backend
```

2. Run the Spring Boot application:

```
./mvnw spring-boot:run
```

3. The backend server will start at:

```
http://localhost:8080
```

Step 4 — Frontend Setup & Run

1. Open a new terminal and navigate to the frontend directory:

```
cd frontend
```

2. Install project dependencies:

```
npm install
```

3. Start the frontend development server:

```
npm run dev
```

4. The frontend will be available at:

```
http://localhost:5173
```

🌐 Live Demo
The app is also deployed online and can be accessed without any local setup:
[https://fast-student-facilitator.vercel.app/](https://fast-student-facilitator.vercel.app/)

📁 Project Structure

```
FAST-Student-Facilitator/
├── backend/
│   ├── src/main/java/com/fast/fsf/
│   │   ├── identity/        # Users & roles
│   │   ├── auth/             # Authentication (incl. Google OAuth)
│   │   ├── timetable/        # Timetable upload, parsing & management
│   │   ├── campusmap/        # Campus locations & navigation
│   │   ├── carpool/          # Ride offers & requests
│   │   ├── pastpapers/       # Past exam papers
│   │   ├── lostfound/        # Lost & found listings
│   │   ├── books/            # Book exchange
│   │   ├── events/           # Campus event board
│   │   ├── reminders/        # Reminders
│   │   ├── admin/            # Admin & moderation
│   │   ├── analytics/        # Stats & reporting
│   │   ├── search/           # Global search
│   │   └── shared/           # Shared domain & persistence (e.g. activity logs)
│   └── pom.xml                # Maven build configuration
├── frontend/
│   ├── src/
│   │   ├── pages/             # Page-level components (Login, Stats, etc.)
│   │   ├── components/        # Reusable UI components
│   │   ├── utils/             # API client & helpers
│   │   └── styles/            # Shared styling primitives
│   └── package.json           # Frontend dependencies & scripts
└── README.md
```

🧩 Design Patterns Used
The backend applies several GoF design patterns across its modules, including Template Method (timetable, campus map, carpool, past papers), State (carpool, past papers, lost & found moderation), Strategy & Composite (campus map and past papers search criteria), Adapter (repository adapters), Factory (entity creation), Observer (event publishing), and Singleton (Spring-managed service/controller beans).

⚠️ Known Limitations

* Campus Map navigation currently covers only major routes and a limited set of locations.
* Some complex Excel timetable layouts with heavily merged cells may produce duplicate entries or incorrect slot positioning.
* Uncommon or malformed date/time inputs (e.g. "Feb 30th") may bypass validation.
* Google OAuth sessions may occasionally be cleared on page refresh in some browsers, requiring re-login.

📄 License
This project is for educational purposes. All rights reserved by the original authors.
