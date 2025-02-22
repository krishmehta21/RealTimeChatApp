# Real-Time Chat App

A real-time chat application built using **Express** and **Socket.io**. This app allows users to join chat rooms, send and receive messages, and view the list of users in a room in real-time.

## Features

- **Real-time Messaging**: Users can send and receive messages in real-time using WebSockets.
- **Multiple Chat Rooms**: Users can join different chat rooms and communicate with others in the same room.
- **User Management**: Users can join and leave rooms, and the list of active users is dynamically updated.
- **Admin Notifications**: The admin sends system messages (e.g., when a user joins or leaves a room).

## Requirements

- **Node.js** (v14.x or higher)
- **npm** (v6.x or higher)

## Installation

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/krishmehta21/RealTimeChatApp.git
   cd RealTimeChatApp/server
   ```

2. Install the required dependencies:

   ```bash
   npm install
   ```

3. Start the server:

   ```bash
   npm run dev
   ```

   The app will start running on `http://localhost:3500`.

## Project Structure

- `server.js`: Main server file handling all the routes, socket connections, and events.
- `public/`: Directory for static files (e.g., HTML, CSS, JS for the frontend).
- `package.json`: Manages dependencies and scripts for the project.
  
## Socket.io Events

The application uses **Socket.io** to manage real-time communication. Here are the events it listens for:

- **`connection`**: Triggered when a user connects.
- **`enterRoom`**: Allows a user to join a room.
- **`disconnect`**: Triggered when a user disconnects.
- **`message`**: Handles sending and receiving messages between users.
- **`activity`**: Tracks the user's activity (typing indicator).
  
## How It Works

- When a user connects, they are greeted with a welcome message.
- The user can then join a room by sending an `enterRoom` event, which joins the room and broadcasts a system message to the room.
- Users can send messages, and these are broadcast to everyone in the same room.
- When a user disconnects, the app broadcasts a message to the room notifying others.

## CORS Configuration

By default, the server only allows connections from `http://localhost:5500` and `http://127.0.0.1:5500` for development purposes. You can change this in the `cors` configuration under `process.env.NODE_ENV === 'production'`.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

You can copy this `README.md` and place it in your project directory. Make sure to update any necessary URLs or specific instructions based on your exact setup.

