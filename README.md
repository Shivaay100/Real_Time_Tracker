# Real-Time Tracker
CLICK ME:https://github.com/Shivaay100/Real_Time_Tracker.git
A real-time location tracking application built with Node.js, Express, Socket.IO, and Leaflet.js. This application allows users to share their live location on a map and view the locations of other connected users in real time.

## Features

- Real-time location sharing using `Socket.IO`.
- Interactive map rendering with `Leaflet.js`.
- Automatically updates the map when users move or disconnect.
- Responsive design for full-screen map display.

## Project Structure

Real_Time_Tracker/
│
├── public/                      # Static files served directly to the client
│   ├── css/
│   │   └── style.css            # Custom styling for full-screen map and UI elements
│   ├── js/
│   │   └── script.js            # Frontend JavaScript (Leaflet map config & Socket.IO client)
│   └── images/                  # (Optional) Custom map markers, icons, or branding assets
│
├── views/                       # Frontend templates/HTML markup
│   └── index.ejs                # Main application view (Embedded JavaScript templates)
│
├── node_modules/                # Generated folder containing installed npm packages
│
├── .gitignore                   # Specifies files and folders for Git to ignore (e.g., node_modules)
├── app.js                       # Main application entry point (Server setup, Express, and Socket.IO)
├── package.json                 # Project metadata, configuration, and dependencies list
└── README.md                    # Project documentation (features, installation, usage)
Installation
Clone the repository:

git clone https://github.com/Shivaay100/Real_Time_Tracker.git


2. **Navigate into the project directory:**
   ```bash
cd Real_Time_Tracker
Install the required dependencies:

npm install


### Running the Application

1. **Start the development server:**
   ```bash
npm start
(Alternatively, if you use nodemon: nodemon app.js)

Open your browser and navigate to:

http://localhost:3000


3. **Allow Location Permissions:** When prompted by your browser, grant location access to see your marker appear instantly on the map. Open the same link in an incognito window or a different device to test multi-user tracking!

---

## 🗺️ Core Architecture & Data Flow

> **How it works:**
> 1. **Client Connection:** When a user opens the app, `public/js/script.js` establishes a connection with the server via WebSockets.
> 2. **GPS Tracking:** The client utilizes `navigator.geolocation.watchPosition()` to stream the device's coordinates.
> 3. **Data Emission:** The client sends a `send-location` event containing `{ latitude, longitude }` to the Node.js backend (`app.js`).
> 4. **Broadcasting:** The server catches the event and broadcasts a `receive-location` event containing the unique `socket.id` and coordinates to all active clients.
> 5. **Map Rendering:** Every connected client receives the broadcast and updates or creates the map marker corresponding to that `socket.id`. When a user closes the tab, the server fires a `disconnect` signal, removing their marker instantly.
