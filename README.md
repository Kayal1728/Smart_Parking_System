[README.md](https://github.com/user-attachments/files/33119805/README.md)
# Smart Parking Management System

An interactive web application for managing a smart parking area. Users can view a live parking map, book available slots, release slots, and monitor parking statistics in real time.

Built with **Python (Flask)**, **SQLite**, and **HTML, CSS, JavaScript**.

---

## Features

- Interactive parking lot map with color-coded slots
  - Green: Available
  - Orange: Reserved
  - Red: Occupied
- Four parking zones
  - Zone A: Standard Parking
  - Zone B: Standard Parking
  - Zone C: EV Parking
  - Zone D: Accessible Parking
- Booking form with owner name, vehicle number, and parking duration
- Booking confirmation popup
- Live statistics: total, available, reserved, and occupied slots, plus occupancy percentage
- Recent booking history
- Release Slot option to make a slot available again
- Mark as Parked option to change a reserved slot to occupied
- Reset Demo option to restore sample data for testing
- Automatic data refresh every 5 seconds
- Responsive design for desktop, tablet, and mobile

---

## Technology Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, CSS3, JavaScript (Fetch API) |
| Backend | Python, Flask |
| Database | SQLite |
| Version Control | Git, GitHub |
| IDE | PyCharm / VS Code |

---

## Project Structure

```
Smart_Parking_System/
├── app.py                  # Flask backend and REST API
├── requirements.txt        # Python dependencies
├── README.md               # Project documentation
├── parking.db              # SQLite database (auto-created)
├── run_windows.bat         # One-click launcher for Windows
├── templates/
│   └── index.html          # Dashboard page
└── static/
    ├── css/
    │   └── style.css       # Styling and responsive layout
    └── js/
        └── app.js          # Interactivity and auto-refresh
```

---

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/Kayal1728/Smart_Parking_System.git
cd Smart_Parking_System
```

### 2. Install dependencies

```bash
py -m pip install -r requirements.txt
```

(On Linux or macOS, use `pip install -r requirements.txt`.)

### 3. Run the application

```bash
py app.py
```

### 4. Open in browser

```
http://127.0.0.1:5000
```

### Run in PyCharm

1. Open the `Smart_Parking_System` folder (File, then Open).
2. Select a Python interpreter (Settings, Project, Python Interpreter).
3. Install requirements using the terminal.
4. Right-click `app.py` and choose **Run 'app'**.

### Run on Windows with one click

Double-click `run_windows.bat`. It creates a virtual environment, installs Flask, and starts the app.

---

## How to Use

1. Click a **green** slot to open the booking form.
2. Enter the owner name, vehicle number, and parking duration, then click **Confirm booking**.
3. The slot turns **orange** and a confirmation popup appears.
4. Click an **orange** slot and choose **Mark as parked** to turn it **red**.
5. Click an **orange** or **red** slot and choose **Release slot** to make it available again.
6. Use **Reset demo** in the header to restore the sample data.

---

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/slots` | Get all slots with booking details |
| GET | `/api/stats` | Get totals and occupancy percentage |
| GET | `/api/bookings` | Get the 10 most recent bookings |
| POST | `/api/book` | Create a new booking |
| POST | `/api/checkin/<id>` | Change a slot from reserved to occupied |
| POST | `/api/release/<id>` | Make a slot available again |
| POST | `/api/reset` | Restore demo data |

---

## Database Schema

**slots**

| Column | Type | Description |
|---|---|---|
| id | INTEGER | Primary key |
| label | TEXT | Slot name (for example A1) |
| zone | TEXT | Zone letter (A, B, C, D) |
| status | TEXT | available, reserved, or occupied |

**bookings**

| Column | Type | Description |
|---|---|---|
| id | INTEGER | Primary key |
| slot_id | INTEGER | Linked slot |
| owner_name | TEXT | Vehicle owner |
| vehicle_number | TEXT | Vehicle registration number |
| duration_hours | INTEGER | Parking duration |
| booked_at | TEXT | Booking time |
| expires_at | TEXT | Booking end time |
| status | TEXT | active or released |

---

## Methodology

The project follows **Agile Methodology** with iterative development of the user interface, slot management, booking and database handling, live statistics, testing, and deployment. **DevOps practices** such as Git and GitHub version control, automated testing, and cloud deployment support continuous integration and delivery.

---

## Future Enhancements

- User login and role-based access (admin and user)
- Automatic slot release when the booking time expires
- Parking fee calculation and payment integration
- QR code based entry and exit
- Charts and reports for parking usage

---

## Author

Kayal Vili RK
