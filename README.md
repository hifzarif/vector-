
# 📍 Vector

A real-time location tracking web application built using **Node.js**, **Socket.IO**, **Leaflet**, and the **Geolocation API**.
It tracks a user’s live geographic location and broadcasts it to connected clients in real time, displaying positions on an interactive map.

---

## 🚀 Features

* 📡 Real-time location sharing using **Socket.IO**
* 🗺️ Interactive map powered by **Leaflet.js**
* 📍 Live GPS tracking via the **HTML5 Geolocation API**
* 🔄 Automatic location updates as the user moves
* 🌍 OpenStreetMap tile integration
* 💻 Multi-user support (can display multiple clients on the same map)

---

## 🛠️ Tech Stack

### Frontend

* HTML
* JavaScript
* Leaflet.js
* OpenStreetMap tiles

### Backend

* Node.js
* Express.js
* Socket.IO

---

## 📦 Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/your-username/realtime-location-tracker.git
   cd realtime-location-tracker
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Start the server**

   ```bash
   node server.js
   ```

   or (if using nodemon)

   ```bash
   nodemon server.js
   ```


   ```

---

## 🗺️ How It Works

1. The browser requests permission to access the user’s location.
2. The **Geolocation API** continuously watches the user’s position.
3. Location data (latitude & longitude) is sent to the server using **Socket.IO**.
4. The server broadcasts location updates to all connected clients.
5. **Leaflet.js** updates markers on the map in real time.

---

## 📄 Sample Client Code (Location Sending)

```js
navigator.geolocation.watchPosition((position) => {
  const { latitude, longitude } = position.coords;
  socket.emit("send-location", { latitude, longitude });
});
```

---

## 🧩 Map Initialization

```js
const map = L.map("map").setView([0, 0], 10);

L.tileLayer("https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png", {
  attribution: "© OpenStreetMap contributors"
}).addTo(map);
```

---

## 🔐 Permissions Required

* **Location Access** (browser will prompt the user)
* HTTPS is recommended for accurate GPS tracking (required by most browsers in production)

---

## 📁 Project Structure

```text
├── public
│   ├── index.html
│   ├── script.js
│   └── style.css
├── server.js
├── package.json
└── README.md
```

---

## 🌟 Future Improvements

* 🧑‍🤝‍🧑 User identification & usernames
* 📌 Persistent markers per user
* 📱 Mobile-friendly UI
* 🔐 Authentication
* 🗄️ Store location history in a database

---

## 🧠 Learning Outcomes

* Real-time communication with Socket.IO
* Browser Geolocation API
* Interactive mapping with Leaflet
* Client–server event handling
* Live data visualization

---



