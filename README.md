# 🛰️ ISS Overhead Notifier

A Python automation project that notifies you via email when the **International Space Station (ISS)** is passing overhead during nighttime at your location. It uses the **Open Notify ISS API**, the **Sunrise–Sunset API**, and **SMTP** to send email alerts.

---

## 📌 Features
- Tracks the **real-time position** of the ISS  
- Checks if the ISS is **within ±5°** latitude/longitude of your location  
- Verifies if it’s **currently nighttime** at your coordinates  
- Sends an **email alert** when both conditions are true  
- Loops every **60 seconds**

---

## 🚀 Getting Started

### 1) Clone the repository
    git clone https://github.com/your-username/iss-overhead-notifier.git
    cd iss-overhead-notifier

### 2) Install dependencies
    pip install requests

### 3) Configure your details
Edit `main.py` and replace with your information:

    MY_LAT = 51.507351    # Your latitude
    MY_LONG = -0.127758   # Your longitude
    MY_EMAIL = "your_email@gmail.com"
    MY_PASS = "your_app_password"

**Important (Gmail users):**
- Use an **App Password** (recommended) for accounts with 2FA.  
- Don’t commit real credentials. Prefer environment variables or a `.env` pattern.

---

## ▶️ Run the script
    python main.py

The script checks once per minute and emails you when the ISS is nearby **and** it’s dark.

---

## 📂 Project Structure
    ├── main.py          # Main Python script
    └── README.md        # Project documentation

---

## 📦 Requirements
- Python 3.x  
- `requests` library (install via `pip install requests`)  
- Internet connection  
- An email account (SMTP: Gmail is used in the sample)

---

## 🔧 How It Works
1. Fetches ISS coordinates from `http://api.open-notify.org/iss-now.json`.  
2. Compares them with your position using a ±5° window.  
3. Retrieves sunrise/sunset times from `https://api.sunrise-sunset.org/json` (ISO format).  
4. Determines if it’s **night** at your location.  
5. If both conditions are true, sends an email using Gmail SMTP (`smtp.gmail.com` with TLS).

---

## ✉️ Example Email
Subject: LOOK UP

The ISS is above you in the sky.
