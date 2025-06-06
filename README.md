# doorbell
Smart Doorbell using WebRTC and Android wrapper

# 🚪 Doorbell App

A smart doorbell system using WebRTC for real-time video/audio communication between the door client (outside) and the home caller (inside). The project includes:

- 📱 Android app (wraps `caller.html` inside a WebView)
- 🌐 Web interface (caller.html + client.html)
- 🔌 Local WebSocket signaling server (Node.js)

## 🔧 Components

### 1. Android App (Caller Side)
- Built using Kotlin
- Foreground service to keep listening for calls
- Loads `caller.html` from local server (e.g., `http://192.168.102.1:3000`)

### 2. Web UIs
- `client.html` → runs on a device mounted outside the door
- `caller.html` → runs on Android (or PC), receives preview + accepts/rejects call

### 3. Signaling Server
- Built using WebSocket (Node.js)
- Facilitates exchange of SDP offers, answers, and ICE candidates

## 🛠 Setup

### Server
```bash
cd web/server
npm install
node server.js
