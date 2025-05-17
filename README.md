# Fitness Node Project

A fitness web application built using Node.js and MongoDB to manage user details, workout plans, nutrition tracking, gym classes, and more.

## Table of Contents

1. [Description](#description)
2. [Features](#features)
3. [Technologies Used](#technologies-used)
4. [Installation Instructions](#installation-instructions)
5. [Usage Instructions](#usage-instructions)
<!-- 6. [Contributing](#contributing) -->

## Description

This project is a fitness application that allows users to:

- Register and authenticate.
- Track their workout plans.
- Keep a record of their nutrition.
- Book gym classes.
- Track exercises, including sets, reps, and intervals.
- Locate nearby gyms with details like amenities and ratings.
- Contact support for assistance.
- View frequently asked questions (FAQs) and health news.

## Features

- **User Authentication**: Users can register and log in using JWT authentication.
- **Work Plans**: Users can create, view, and manage their fitness work plans.
- **Nutrition Tracker**: Users can log their meals and track calories, proteins, fats, and carbs.
- **Gym Classes**: Users can view and book gym classes with a given time.
- **Exercise Tracker**: Track exercises including name, description, repetitions, sets, and intervals.
- **Gym Locator**: Find nearby gyms with location, amenities, and ratings.
- **Contact Support**: Send a message to the support team for any inquiries.
- **FAQs**: View frequently asked questions with answers.
- **Health News**: Stay up-to-date with the latest health news.

## Technologies Used

- **Node.js** – Backend framework
- **Express** – Web framework for Node.js
- **MongoDB (Native Driver)** – NoSQL database (No Mongoose used)
- **JWT (JSON Web Token)** – For user authentication
- **Bcryptjs** – For password hashing
- **dotenv** – For managing environment variables

## Installation Instructions

### Prerequisites

- Install **Node.js** and **npm** on your machine.
- Set up **MongoDB** locally or use a cloud service like MongoDB Atlas.

### Steps

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/YourUsername/fitness-node.git
   ```

2. **Navigate to the project directory**:

    ```bash
    cd fitness-node
    ```

3. **Install dependencies**:

    ```bash
    npm install

    ```

4. **Configure Database URI and JWT Secret**:

    Open the Constants/config.js file and update the MongoDB URI and JWT Secret:

    ```js
    // Constants/config.js

    module.exports = {
        DB_URI: 'mongodb://localhost:27017/fitnessdb', // Your MongoDB URI
        JWT_SECRET: 'your_jwt_secret_key',             // Your JWT secret key
    };
    ```

5. **Start the server**:

    ```bash
    npm start
    ```

    The server will run on localhost:3000 by default.

## Usage Instructions

Once the server is running, you can interact with the API using tools like **Postman**, **Insomnia**, or any frontend client.

### Base URL

<http://localhost:3000/>

---

### 🔐 User Authentication & Profile Routes

1. **Register a new user**

   - **POST** `/user/signup`
   - **Middleware**: `validateSignInUser`
   - **Body Example**:

     ```json
     {
       "name": "John Doe",
       "email": "john@example.com",
       "password": "yourpassword"
     }
     ```

2. **Login an existing user**

   - **POST** `/user/login`
   - **Middleware**: `validateLoginInUser`
   - **Body Example**:

     ```json
     {
       "email": "john@example.com",
       "password": "yourpassword"
     }
     ```

3. **Get user profile**

   - **GET** `/user/profile`
   - **Headers**:

     ```
     Authorization: Bearer <your_token>
     ```

4. **Update user profile (with profile image)**

   - **PUT** `/user/profile`
   - **Middleware**: `Auth`, `profileImage`, `validateUpdateUser`
   - **Headers**:

     ```
     Authorization: Bearer <your_token>
     ```

   - **Form Data** (Content-Type: multipart/form-data):
     - `name`: New name (optional)
     - `email`: New email (optional)
     - `image`: Profile image file (optional)

---

> Replace `<your_token>` with the JWT token returned during login.

This section now clearly outlines your current route structure, what each route does, how to use them, and the necessary headers or body formats.

<!-- ## Contributing

This project is maintained as a personal portfolio/demo.
Please do not submit pull requests or open issues. -->
