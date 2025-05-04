Video Chat App with Drawing and Screen Sharing
Overview
This project is a real-time video chat application with additional features including drawing on the screen and screen sharing. It uses technologies like PeerJS, Socket.IO, and WebRTC to enable peer-to-peer video communication. The app also includes a drawing canvas where users can annotate on the screen while maintaining an interactive video call experience.

Features
Real-Time Video Chat: Users can join a video room and see each other in real-time.

Screen Sharing: Users can share their screen with others in the call.

Drawing Feature: Users can draw on a canvas during the video chat.

Responsive Layout: The app is responsive and works across different screen sizes.

Technologies Used
PeerJS: For peer-to-peer connections to enable video chat functionality.

Socket.IO: To handle communication between the server and clients.

WebRTC: For real-time video and audio streaming.

HTML5 Canvas: For drawing functionality on top of the video chat.

CSS: For styling the application, including responsive layouts and button designs.

Prerequisites
To run this application, ensure you have the following:

Node.js (version 14 or later)

npm (Node Package Manager)

Setup and Installation
Follow the steps below to set up the project on your local machine:

1. Clone the repository
bash
Copy
Edit
git clone https://github.com/your-username/video-chat-app.git
cd video-chat-app
2. Install dependencies
Run the following command to install the required dependencies:

bash
Copy
Edit
npm install
3. Set up your server
You will need to set up a Node.js server for handling the application logic and WebRTC connections.

The server will handle the Socket.IO connection and will generate a unique roomId for each video chat session.

4. Run the application
Start the server:

bash
Copy
Edit
npm start
This will run the app on http://localhost:3000 (or any other port you specify in your server setup).

5. Access the app
Open your browser and navigate to http://localhost:3000 to join a video chat room. Share the room URL with others to join the same session.

Features Explanation
Video Chat
Once a user joins the room, they will be able to see the video stream of all participants in the room.

The video grid dynamically adjusts as new participants join or leave the session.

Screen Sharing
Click on the Share Screen button to start sharing your screen with others in the video room.

Once screen sharing is started, a new video stream showing your screen will appear in the video grid.

When screen sharing is stopped, the video stream is removed, and an alert notifies the user.

Drawing Feature
Click on the Enable Draw button to activate the drawing canvas.

Once drawing is enabled, you can draw freely on the screen using your mouse or touch.

The Disable Draw button will clear the drawing and stop the drawing feature.

Important: The drawing canvas only overlays on top of the video and prevents interaction with the video grid. This ensures that you cannot click on the video grid while drawing.

Responsive Design
The layout automatically adjusts based on the screen size.

The video grid is displayed in a responsive grid format, and the canvas takes up the entire screen when drawing is enabled.

Code Explanation
HTML Structure
Video Grid: Displays the video streams of all users in the room.

Canvas: Positioned over the video grid to allow drawing.

Footer: Contains the control buttons like Hang Up, Share Screen, and Enable Draw.

CSS Styling
The video-grid is displayed as a responsive grid with a gap of 1rem between the video elements.

The canvas is initially hidden under the video grid with pointer-events: none. It is only made interactive when the drawing feature is enabled.

The footer buttons are styled with different colors for actions such as hang up, screen share, and draw.

JavaScript Functions
startScreenShare(): Starts screen sharing by requesting the user’s screen using navigator.mediaDevices.getDisplayMedia(). It appends the shared screen to the video grid and handles the ending of the screen share.

toggleDraw(): Toggles the drawing functionality. When enabled, it allows the user to draw on the screen; otherwise, the canvas is cleared.

resizeCanvas(): Resizes the canvas to match the window size, ensuring full-screen drawing capabilities.

Event Listeners
Mouse events are used for drawing functionality:

mousedown: Starts drawing.

mousemove: Draws on the canvas.

mouseup and mouseout: Stops drawing when the mouse button is released or the mouse leaves the canvas area.

Socket.IO and PeerJS Integration
PeerJS handles peer-to-peer communication for video streaming.

Socket.IO allows for room management, signaling, and broadcasting events such as user connections and disconnections.

Future Improvements
User Authentication: Add user authentication to manage users in rooms more effectively.

Private Messaging: Implement a private messaging feature during video calls.

File Sharing: Allow users to share files during a video chat.

Better UI/UX: Improve the interface with more user-friendly designs and animations.

Contributing
Feel free to fork the repository and submit issues or pull requests if you'd like to contribute to the project.
