Here’s an improved version of your **README.md** that organizes the information more effectively and adds a bit more detail to make it clearer for other developers or contributors:

---

# Video Chat App with Drawing and Screen Sharing

## Overview

This project is a **real-time video chat application** with additional features like **drawing on the screen** and **screen sharing**. It leverages technologies such as **PeerJS**, **Socket.IO**, and **WebRTC** to provide seamless video communication between users. The app also includes a **drawing canvas** where users can annotate the screen during video calls. The application has a **responsive layout** to adapt across various screen sizes.

## Features

* **Real-Time Video Chat**: Users can join a video room and view live video streams of participants.
* **Screen Sharing**: Users can share their screen with others in the call.
* **Drawing Feature**: Users can draw on a canvas overlay while in the video chat.
* **Responsive Design**: The layout adjusts based on screen size, ensuring a user-friendly experience on all devices.

## Technologies Used

* **PeerJS**: Manages peer-to-peer video connections.
* **Socket.IO**: Handles real-time communication for signaling and room management.
* **WebRTC**: Powers real-time audio and video streaming.
* **HTML5 Canvas**: Provides the drawing surface over the video chat.
* **CSS**: Custom styles for a responsive and user-friendly interface.

## Prerequisites

To run this application locally, you will need the following:

* **Node.js** (version 14 or later)
* **npm** (Node Package Manager)

## Setup and Installation

Follow these steps to get the project running on your local machine:

### 1. Clone the repository

```bash
git clone https://github.com/your-username/video-chat-app.git
cd video-chat-app
```

### 2. Install dependencies

Run the following command to install the necessary dependencies:

```bash
npm install
```

### 3. Set up your server

You will need a Node.js server to handle application logic and WebRTC signaling.

* The server handles **Socket.IO** connections and generates a unique `roomId` for each video chat session.
* This server also manages peer connections through **PeerJS**.

### 4. Start the application

Start the server with:

```bash
npm start
```

This will launch the app on `http://localhost:3000` (or another port if specified in your server setup).

### 5. Access the app

Open your browser and go to `http://localhost:3000` to join a video chat room. Share the room URL with others to join the same session.

## Features Explained

### Video Chat

* Once a user joins the room, they can see the video streams of all other participants in real-time.
* The video grid will adjust automatically as users join or leave the call.

### Screen Sharing

* Click the **Share Screen** button to start sharing your screen with others in the video room.
* A new video stream showing your screen will be added to the video grid.
* When screen sharing is stopped, the video stream will be removed, and users will be notified.

### Drawing Feature

* Clicking the **Enable Draw** button activates the drawing canvas.
* Users can draw freely on the screen using their mouse or touch.
* Clicking the **Disable Draw** button clears the canvas and disables drawing.

**Important:** When drawing is enabled, interaction with the video grid is disabled. This prevents accidental clicks on the videos while drawing.

### Responsive Design

* The layout automatically adjusts based on the screen size.
* The video grid uses a responsive grid format, and the drawing canvas covers the entire screen when enabled.

## Code Explanation

### HTML Structure

* **Video Grid**: Displays video streams of all room participants.
* **Canvas**: Positioned over the video grid for drawing.
* **Footer**: Contains action buttons such as **Hang Up**, **Share Screen**, and **Enable Draw**.

### CSS Styling

* The **video-grid** is styled to be responsive, displaying video elements with a gap between them.
* The **canvas** is initially hidden under the video grid, but is made interactive when drawing is enabled (`pointer-events: auto`).
* Buttons in the footer are styled to differentiate between actions (e.g., red for hang up, blue for share screen, and purple for enabling drawing).

### JavaScript Functions

* **startScreenShare()**: Starts screen sharing using `navigator.mediaDevices.getDisplayMedia()`. It adds a video stream of the shared screen to the video grid.
* **toggleDraw()**: Toggles the drawing functionality. When enabled, users can draw on the screen; disabling it clears the canvas.
* **resizeCanvas()**: Resizes the canvas dynamically based on the window size to maintain full-screen drawing.

### Event Listeners

Mouse events are used for the drawing functionality:

* **mousedown**: Starts drawing.
* **mousemove**: Draws on the canvas as the mouse moves.
* **mouseup** and **mouseout**: Stops drawing when the mouse button is released or the mouse leaves the canvas.

### Socket.IO and PeerJS Integration

* **PeerJS** manages peer-to-peer connections for video streams.
* **Socket.IO** is used to manage signaling for connecting users, room management, and broadcasting events like user joins and leaves.

## Future Improvements

* **User Authentication**: Add a user authentication system to manage users and their video rooms more securely.
* **Private Messaging**: Implement private chat functionality during video calls.
* **File Sharing**: Allow users to share files during the video call.
* **Improved UI/UX**: Enhance the user interface with better animations and intuitive designs.

## Contributing

Feel free to fork the repository, create pull requests, or report issues. If you'd like to contribute, please follow the standard GitHub flow:

1. Fork the repository.
2. Create a feature branch.
3. Implement your changes.
4. Open a pull request.

---
