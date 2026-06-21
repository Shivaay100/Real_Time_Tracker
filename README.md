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
