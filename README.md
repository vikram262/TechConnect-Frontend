# TechConnect-Frontend

TechConnect-Frontend, also known as Dev Tinder Web, is a social networking platform designed to help developers connect with each other. This project is a frontend application built with React and leverages various modern web technologies to provide a seamless user experience.

## Table of Contents

* [Features](#features)

* [Technologies Used](#technologies-used)

* [Project Structure](#project-structure)

* [Setup and Installation](#setup-and-installation)

* [API Endpoints (Backend Interaction)](#api-endpoints-backend-interaction)

* [Styling](#styling)

* [State Management](#state-management)

* [Real-time Communication](#real-time-communication)

* [Payment Integration](#payment-integration)

## Features

TechConnect-Frontend offers the following key functionalities:

* **User Authentication**: Users can sign up for new accounts or log in with existing credentials.

* **Profile Management**: Users can view and edit their profiles, including details like first name, last name, photo URL, age, gender, and a short "about" section.

* **User Feed**: Displays a feed of other users, allowing the current user to express interest or ignore them.

* **Connection Management**: Users can view their established connections and manage received connection requests, accepting or rejecting them.

* **Real-time Chat**: Integrated chat functionality allows users to communicate with their connections in real-time.

* **Premium Membership**: Offers different premium membership tiers (Silver and Gold) with enhanced features, integrated with Razorpay for payments.

* **Responsive Navigation**: A navigation bar that adapts to different screen sizes and provides access to various sections of the application.

## Technologies Used

The project is built using the following technologies:

* **Frontend Framework**:

    * [React](https://react.dev/)

    * [Vite](https://vitejs.dev/) (Build Tool)

* **State Management**:

    * [Redux Toolkit](https://redux-toolkit.js.org/)

    * React Redux

* **Routing**:

    * [React Router DOM](https://reactrouter.com/en/main)

* **API Communication**:

    * [Axios](https://axios-http.com/)

* **Styling**:

    * [Tailwind CSS](https://tailwindcss.com/)

    * [DaisyUI](https://daisyui.com/) (Tailwind CSS Component Library)

* **Real-time Communication**:

    * [Socket.IO Client](https://socket.io/docs/v4/client-api/)

* **Code Quality**:

    * [ESLint](https://eslint.org/)

* **Payment Gateway**:

    * [Razorpay Checkout](https://razorpay.com/docs/api/payments/checkout/)

## Project Structure

The project follows a standard React application structure:
├── public/
├── src/
│   ├── components/
│   │   ├── Body.jsx
│   │   ├── Chat.jsx
│   │   ├── Connections.jsx
│   │   ├── EditProfile.jsx
│   │   ├── Feed.jsx
│   │   ├── Footer.jsx
│   │   ├── Login.jsx
│   │   ├── NavBar.jsx
│   │   ├── Premium.jsx
│   │   ├── Profile.jsx
│   │   ├── Requests.jsx
│   │   └── UserCard.jsx
│   ├── utils/
│   │   ├── appStore.js
│   │   ├── conectionSlice.js
│   │   ├── constants.js
│   │   ├── feedSlice.js
│   │   ├── requestSlice.js
│   │   ├── socket.js
│   │   └── userSlice.js
│   ├── App.jsx
│   ├── index.css
│   └── main.jsx
├── .gitignore
├── eslint.config.js
├── index.html
├── package-lock.json
├── package.json
├── postcss.config.js
├── README.md
└── tailwind.config.js
├── vite.config.js

## Setup and Installation

To set up and run the project locally, follow these steps:

1.  **Prerequisites**:

    * Node.js (>= 18.0.0 or >= 20.0.0)

    * npm or Yarn

2.  **Clone the repository**:

    ```bash
    git clone <repository-url>
    cd TechConnect-Frontend
    ```

3.  **Install dependencies**:

    ```bash
    npm install
    # or
    yarn install
    ```

4.  **Backend Setup**: This frontend project requires a corresponding backend server to function correctly. Ensure your backend is running and accessible at the `BASE_URL` defined in `src/utils/constants.js`.

    * For local development, the `BASE_URL` is set to `http://localhost:7777`.

    * For production, it uses `/api`.

5.  **Run the development server**:

    ```bash
    npm run dev
    # or
    yarn dev
    ```

    This will start the Vite development server, usually on `http://localhost:5173`.

## API Endpoints (Backend Interaction)

The frontend interacts with the backend using Axios. Key API endpoints used include:

* `/login`: User login.

* `/signup`: User registration.

* `/logout`: User logout.

* `/profile/view`: Fetch user profile information.

* `/profile/edit`: Update user profile details.

* `/feed`: Get a list of users for the feed.

* `/request/send/:status/:userId`: Send a connection request (interested/ignored).

* `/user/connections`: Fetch established connections.

* `/user/requests/received`: Fetch received connection requests.

* `/request/review/:status/:_id`: Review a received connection request (accepted/rejected).

* `/premium/verify`: Check premium membership status.

* `/payment/create`: Initiate a payment for premium membership.

* `/chat/:targetUserId`: Fetch chat messages for a specific user.

All API calls requiring authentication send credentials with the request (`withCredentials: true`).

## Styling

The application's UI is built using:

* **Tailwind CSS**: A utility-first CSS framework for rapidly building custom designs.

* **DaisyUI**: A Tailwind CSS component library that provides pre-built UI components.

## State Management

The application utilizes [Redux Toolkit](https://redux-toolkit.js.org/) for efficient state management. The main store is configured in `src/utils/appStore.js` and includes the following slices:

* `userSlice`: Manages user authentication and profile data.

* `feedSlice`: Manages the user feed data.

* `connectionSlice`: Manages user connections data.

* `requestSlice`: Manages incoming connection requests.

## Real-time Communication

Real-time chat functionality is implemented using [Socket.IO](https://socket.io/). The `createSocketConnection` utility handles establishing and managing the socket connection.

## Payment Integration

Premium memberships are handled through integration with [Razorpay](https://razorpay.com/). The Razorpay Checkout script is loaded directly in `index.html`, and payment creation is managed by the `Premium` component.
