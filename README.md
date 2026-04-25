🚀 UniHop | Campus Rides
UniHop is a real-time web application designed exclusively for university students to share rides, save money on travel, and reduce their carbon footprint. Skip the bus, split the fare, and hop in a car with verified peers!

✨ Key Features
Real-Time Ride Chat: Integrated live messaging using WebSockets (Flask-SocketIO) so drivers and passengers can coordinate instantly.

Global Driver Pinging: A global notification system that alerts drivers to new pings no matter what page they are browsing.

Live Campus Routing: An interactive map powered by Leaflet.js and OpenStreetMap that draws the exact route from pickup to destination.

Smart Dashboard: Auto-filters past rides so users only see upcoming, available trips.

Request Management System: Drivers can seamlessly Accept or Reject passenger requests, which updates the ride capacity automatically.

Mobile-Responsive UI: Custom CSS with a "Vibrant Aurora" dark glass theme, animated stat counters, and a dynamic mobile hamburger menu.

🛠️ Tech Stack
Backend: Python, Flask

Database: SQLite (managed via Flask-SQLAlchemy)

Real-Time Communication: Flask-SocketIO

Frontend: HTML5, CSS3, Vanilla JavaScript, Jinja2 Templating

Maps & Routing: Leaflet.js & Leaflet Routing Machine

💻 Local Setup & Installation
If you want to run this project on your local machine, follow these steps:

1. Clone the repository

Bash
git clone https://github.com/yourusername/unihop.git
cd unihop
2. Create a virtual environment (Optional but recommended)

Bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
3. Install dependencies
Make sure your requirements.txt file only contains the necessary Flask packages (remove any Windows-specific packages like pywinpty if deploying to Linux).

Bash
pip install -r requirements.txt
4. Run the application

Bash
python app.py
The application will automatically generate the carpooling.db database file on the first run. Open your browser and navigate to http://127.0.0.1:5000.

🌐 Deployment Notes (Render.com)
This application is configured for easy deployment on Render.

To deploy successfully:

Ensure your app.py ends with the correct port and Werkzeug bypass:

Python
if __name__ == "__main__":
    port = int(os.environ.get("PORT", 5000))
    socketio.run(app, host="0.0.0.0", port=port, allow_unsafe_werkzeug=True)
Set your Build Command to: pip install -r requirements.txt

Set your Start Command to: python app.py

(Note: Render's free tier uses an ephemeral file system. For a full production launch, it is recommended to swap the SQLite database URI for a managed PostgreSQL instance).

📄 License
© 2026 UniHop. Built for students.
