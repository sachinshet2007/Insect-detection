# 🐛 Insect Detection & Monitoring System

This project is a **real-time insect detection and monitoring system** using:

- Raspberry Pi
- Camera Module (Picamera2)
- Ultrasonic Sensor (HC-SR04)
- Roboflow AI Model
- Flask Web Dashboard
- SQLite Database
- Cloudinary (Image Hosting)
- Twilio (SMS Alerts)

---

## 🚀 Features

- 📸 Automatic image capture when object detected
- 🧠 AI-based insect classification (Roboflow)
- 📊 Real-time web dashboard (Flask + Socket.IO)
- ☁️ Image upload to Cloudinary
- 📩 SMS alerts with image (Twilio)
- 🗄️ Data storage using SQLite
- 📈 Live chart visualization
- 🔍 Filter insects by type

---

## 🏗️ System Architecture


Ultrasonic Sensor → Raspberry Pi → Camera Capture
↓
Roboflow API (Detection)
↓
Cloudinary (Image Upload)
↓
Flask Server (Database + Dashboard)
↓
Twilio SMS Alert


---

## 📁 Project Structure


├── detect.py # Main Raspberry Pi detection script
├── server.py # Flask dashboard server
├── data.db # SQLite database (auto-created)
└── images/ # Captured images (temporary)


---

## ⚙️ Hardware Requirements

- Raspberry Pi (with GPIO support)
- Camera Module (Picamera2)
- Ultrasonic Sensor (HC-SR04)
- LED (optional indicator)
- Jumper wires

---

## 🔧 Software Requirements

Install dependencies:

```bash
pip install requests flask flask-socketio cloudinary twilio picamera2 RPi.GPIO
🔑 Configuration
1. Roboflow API

Update in detect.py:

API_KEY = "YOUR_ROBOFLOW_API_KEY"
MODEL_ID = "your_model/version"

2. Twilio Setup
ACCOUNT_SID = "YOUR_TWILIO_SID"
AUTH_TOKEN = "YOUR_TWILIO_AUTH_TOKEN"
FROM_NUMBER = "+1234567890"
TO_NUMBER = "+91XXXXXXXXXX"

3. Cloudinary Setup
cloudinary.config(
    cloud_name="YOUR_CLOUD_NAME",
    api_key="YOUR_API_KEY",
    api_secret="YOUR_API_SECRET"
)

4. Flask Server Endpoint

Set your server IP:

ENDPOINT = "http://<YOUR_SERVER_IP>:5000/data/ingest"

▶️ How to Run
Step 1: Start Flask Server
python server.py

Server will run at:

http://0.0.0.0:5000

Step 2: Run Detection Script (Raspberry Pi)
python detect.py

📊 Dashboard Features
🐞 View detected insects
🖼️ Image preview
📅 Timestamp tracking
📉 Confidence levels (High / Medium / Low)
🍩 Doughnut chart visualization
🔄 Live auto-refresh using WebSockets

🔁 Workflow
Ultrasonic sensor detects object (< 20 cm)
Camera captures image
Image sent to Roboflow API
Insect detected & classified
Image uploaded to Cloudinary
Data sent to Flask server
Dashboard updates in real-time
SMS alert sent with image

📜 License

This project is open-source and free to use.
