# Submission Details

## Project Name: Contest Tracker

### Submission Link

[Client GitHub Repo](https://github.com/Ayush05m/CodePulse-Contest_Tracker_Client)
[Server GitHub Repo](https://github.com/Ayush05m/CodePulse-Contest_Tracker_Server)

---

## Deployed Link

Hosted on Vercel & Render: [Live](https://code-pulse-contest-tracker-client.vercel.app/)

---

## Project Overview

The **Contest Tracker** is a full-stack web application that tracks programming contests from multiple platforms and allows users to bookmark contests, attach solutions, and retrieve contest details.

## Codebase Contents

- **Backend Code**: Node.js, Express.js, MongoDB, TypeScript.
- **Frontend Code**: React.js, Vite, TanStack React Query, TailwindCSS, Redux.
- **Product Walkthrough Video**: [Video]()
- **Documentation**: Setup, API details, features, and deployment instructions.

---

# Contest Tracker Fullstack Documentation

## Overview

The **Contest Tracker** is a full-stack web application built with **TypeScript, Node.js, Express.js (backend), and React.js (frontend)**. It tracks programming contests across multiple platforms and allows users to bookmark contests, attach solutions, and retrieve contest details.

## Features

- User authentication with JWT.
- Fetching programming contest details from **Codeforces, CodeChef, LeetCode**.
- Bookmarking contests for easy access.
- Attaching solution links to past contests.
- Fetching YouTube videos related to contests.
- Caching services for optimized performance.

---

## Backend Setup

### Prerequisites

Ensure you have the following installed:

- **Node.js** (v16 or later)
- **MongoDB** (local or cloud instance)

### Steps to Install (Backend)

1. Fork & Clone the repository:
   ```sh
   git clone https://github.com/your-repo/contest-tracker.git
   cd contest-tracker
   ```
2. Install dependencies:
   ```sh
   npm install
   ```
3. Create a `.env` file and configure environment variables:
   ```sh
   PORT=5000
   MONGO_URI=mongodb://localhost:27017/contest_tracker
   JWT_SECRET=your_jwt_secret
   YOUTUBE_API_KEY=your_youtube_api_key
   ```
4. Start the development server:
   ```sh
   npm run dev
   ```

## API Endpoints

### Authentication (current not connected)

#### Register User

- **Endpoint:** `POST /api/auth/register`
- **Description:** Registers a new user.
- **Request Body:**
  ```json
  {
    "username": "user123",
    "email": "user@example.com",
    "password": "password123"
  }
  ```
- **Response:**
  ```json
  {
    "message": "User registered successfully"
  }
  ```

#### Login User

- **Endpoint:** `POST /api/auth/login`
- **Description:** Logs in an existing user and returns a JWT token.
- **Request Body:**
  ```json
  {
    "email": "user@example.com",
    "password": "password123"
  }
  ```
- **Response:**
  ```json
  {
    "token": "your_jwt_token"
  }
  ```

### Contests

#### Get All Contests

- **Endpoint:** `GET /api/contests`
- **Description:** Fetches upcoming and past contests from multiple platforms.

#### Get Contest by ID

- **Endpoint:** `GET /api/contests/:id`
- **Description:** Fetches details of a specific contest.

### Bookmarks

###### Currently working with redux and localstorage, bookmark api are for future implementation

#### Add Bookmark

- **Endpoint:** `POST /api/bookmarks`
- **Description:** Adds a contest to the user's bookmarks.
- **Request Body:**
  ```json
  {
    "contestId": "12345"
  }
  ```

#### Get Bookmarks

- **Endpoint:** `GET /api/bookmarks`
- **Description:** Fetches all bookmarked contests for the user.

### Solutions

#### Get Contest Solution

- **Endpoint:** `GET /api/solutions`
- **Description:** Allows users to get all available solution links .
- **Respose:**
  ```json
  {
      "success": true,
      "count": "number",
      "pagination": {},
      "data": [{
         "contest_id": "mongoose.Types.ObjectId",
         "youtubeLinks": {
            "url": "string",
            "title": "string",
            "description"?: "string",
            "thumbnail": "string",
         }[],
         "submittedBy": "mongoose.Types.ObjectId",
         "votes": {
            "upvotes": "number",
            "downvotes": "number",
         },
         "createdAt": "Date",
         "updatedAt": "Date",
      }],
    }
  ```

#### Get Solutions for a Contest

- **Endpoint:** `GET /api/solutions/:contestId`
- **Description:** Fetches all solutions for a specific contest.

---

## Frontend Setup

### Prerequisites

Ensure you have the following installed:

- **Node.js** (v16 or later)
- **React.js** with Vite

### Steps to Install (Frontend)

1. Navigate to the frontend directory:
   ```sh
   cd frontend
   ```
2. Install dependencies:
   ```sh
   npm install
   ```
3. Start the development server:
   ```sh
   npm run dev
   ```

### Pages & Routes

The frontend is built with **React + React Router** and uses **TanStack React Query** for data fetching.

| Route        | Component     | Description                  |
| ------------ | ------------- | ---------------------------- |
| `/`          | HomePage      | Landing page                 |
| `/contests`  | ContestsPage  | List of contests             |
| `/bookmarks` | BookmarksPage | User's bookmarked contests   |
| `/solutions` | SolutionsPage | Solutions linked to contests |
| `/login`     | LoginPage     | User login form              |
| `/register`  | RegisterPage  | User registration form       |
| `*`          | NotFoundPage  | 404 Not Found                |

### State Management

- Uses **TanStack Query (React Query)** for API calls.
- Uses **React Router** for navigation.
- Uses **ThemeProvider** for light/dark mode toggle.
- Uses **Redux** for bookmarks and notes handles.

---

## Caching Services

- The backend implements caching using **Redis (or an alternative in-memory solution)** to improve performance for frequently accessed contest data.

## Deployment

- To deploy, use a cloud service like **AWS, DigitalOcean, or Vercel**.
- Set up a production database and update the `.env` file accordingly.
- Run the production build:
  ```sh
  npm run build
  npm start
  ```

## Contributing

1. Fork the repository.
2. Create a new branch: `git checkout -b feature-branch`
3. Commit your changes: `git commit -m 'Add new feature'`
4. Push to the branch: `git push origin feature-branch`
5. Open a pull request.

## License

This project is licensed under the **MIT License**.

---

For further assistance, feel free to reach out or create an issue in the repository.

---

For any queries, feel free to reach out!
