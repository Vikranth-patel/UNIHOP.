# 🚗 UniHop | Campus Rides - Real-time Carpooling Platform

> A modern, real-time web application designed for university students to share rides, split fares, and reduce their carbon footprint. Skip the bus, split the fare, and hop in! 🚀

![Status](https://img.shields.io/badge/status-active-brightgreen)
![License](https://img.shields.io/badge/license-EPL%202.0-blue)
![Python](https://img.shields.io/badge/python-3.7+-blue)
![Build](https://img.shields.io/badge/build-passing-brightgreen)

---

## 🎯 Project Vision

UniHop transforms campus transportation by connecting students who share similar routes. Whether you're heading to class, the library, or across the city, find a ride-mate, split costs, and make friends along the way.

**Key Benefits:**
- 💰 Save money on travel
- 🌍 Reduce carbon footprint
- ⏱️ Real-time coordination
- 👥 Build campus community
- 🛣️ Flexible, peer-to-peer pricing

---

## ✨ Core Features

### 🚀 Real-Time Ride Chat
- **WebSocket-powered messaging** using Flask-SocketIO
- **Instant communication** between drivers and passengers
- **No page refresh needed** - messages appear in real-time
- **Chat History** - persistent conversations for each ride
- **Ping Driver** - alert drivers with highlighted notifications

### 🌍 Global Driver Pinging
- **Instant notifications** visible across all pages
- **Highlighted alerts** that grab attention
- **Status indicators** for ride availability
- **Smart notification routing** - drivers notified instantly

### 🗺️ Live Campus Routing
- **Interactive Leaflet.js maps** with OpenStreetMap integration
- **Route visualization** from pickup to destination
- **Campus location markers** with key landmarks
- **Route optimization** suggestions
- **Boundary-based filtering** (stay on campus)

### 📊 Smart Dashboard
- **Auto-filters** to show only upcoming rides
- **Availability status** at a glance
- **Quick action buttons** for ride requests
- **Real-time ride statistics** (rides offered, requested, completed)
- **Animated counters** showing platform activity

### 🎛️ Request Management System
- **Driver controls** - Accept/Reject passenger requests
- **Automatic capacity updates** as passengers join
- **Request status tracking** (Pending → Accepted → Completed)
- **One-click request management**
- **Request history** with timestamps

### 📱 Mobile-Responsive UI
- **"Vibrant Aurora" dark glass theme** - modern & sleek
- **Animated stat counters** showing live data
- **Dynamic hamburger menu** for mobile navigation
- **Touch-optimized buttons** and inputs
- **Responsive breakpoints** for all device sizes

### 👤 User Profile Management
- **Profile customization** with avatar and bio
- **Ride statistics** (rides offered, requested, completed)
- **Rating system** (future enhancement)
- **Contact information** for safety
- **Ride history** tracking

### 🔒 Secure Authentication
- **User sign-up & login** system
- **Session management** with Flask sessions
- **Password security** best practices
- **Form validation** on client and server

---

## 🛠️ Technology Stack

| Layer | Technology |
|-------|-----------|
| **Backend** | Python 3.7+, Flask Web Framework |
| **Database** | SQLite with SQLAlchemy ORM |
| **Real-Time** | Flask-SocketIO (WebSockets) |
| **Frontend** | HTML5, CSS3, Vanilla JavaScript, Jinja2 |
| **Maps & Routing** | Leaflet.js, OpenStreetMap, Leaflet Routing Machine |
| **Server** | Werkzeug, Gunicorn (production) |

---

## 📦 Installation & Setup

### Prerequisites
- **Python 3.7+** installed
- **pip** (Python package manager)
- **Modern web browser** (Chrome, Firefox, Safari, Edge)
- **~50MB** disk space

### Step 1: Clone the Repository

```bash
git clone https://github.com/Vikranth-patel/UNIHOP.git
cd UNIHOP
cd carpooling-app-main
```

### Step 2: Create Virtual Environment (Recommended)

```bash
# On macOS/Linux
python -m venv venv
source venv/bin/activate

# On Windows
python -m venv venv
venv\Scripts\activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

**What gets installed:**
- Flask (web framework)
- Flask-SQLAlchemy (database ORM)
- Flask-SocketIO (real-time messaging)
- python-socketio (WebSocket support)
- Werkzeug (WSGI toolkit)
- Jinja2 (templating)

### Step 4: Run the Application

```bash
python app.py
```

**Expected output:**
```
 * Running on http://127.0.0.1:5000
 * WARNING: This is a development server. Do not use it in production.
```

### Step 5: Access the Application

Open your browser and navigate to:
```
http://localhost:5000
```

---

## 📖 First-Time User Guide

### For Passengers 🚗

1. **Create Account**
   - Click "Sign Up"
   - Enter name, email, phone, password
   - Create your profile

2. **Find a Ride**
   - Go to Dashboard
   - Browse available rides on the map
   - Click "Request Ride" on your desired ride

3. **Communicate with Driver**
   - Use Ping Driver feature to notify driver
   - Once accepted, open Chat to discuss:
     - Pickup location details
     - Exact time
     - Fare amount
     - Special requirements

4. **Complete the Ride**
   - Get in and enjoy!
   - Rate the driver (future feature)
   - Leave a comment

### For Drivers 🚙

1. **Create Account**
   - Sign up with vehicle details
   - Complete driver profile

2. **Offer a Ride**
   - Click "Offer Ride"
   - Enter:
     - Origin location
     - Destination location
     - Departure time
     - Available seats
     - Optional: Base fare (or let passengers suggest)

3. **Manage Requests**
   - View pending requests in My Rides
   - Accept passengers (seats decrease automatically)
   - Reject requests as needed

4. **Coordinate Journey**
   - Use Chat to confirm details with each passenger
   - Discuss final fare
   - Provide pickup instructions
   - Complete the ride

---

## 🗂️ Project Structure

```
UNIHOP/
└── carpooling-app-main/
    ├── app.py                      # Flask application entry point
    ├── models.py                   # Database models (User, Ride, etc.)
    ├── requirements.txt            # Python dependencies
    ├── README.md                   # Project documentation
    ├── QUICKSTART.md              # Quick setup guide
    │
    ├── templates/                  # HTML Templates (Jinja2)
    │   ├── base.html              # Base layout template
    │   ├── index.html             # Landing page
    │   ├── login.html             # Login page
    │   ├── signup.html            # Registration page
    │   ├── dashboard.html         # Main dashboard with rides
    │   ├── offer_ride.html        # Create new ride form
    │   ├── my_rides.html          # User's rides management
    │   ├── profile.html           # User profile page
    │   ├── map.html               # Interactive map view
    │   └── chat.html              # Real-time chat interface
    │
    └── static/                     # Static Assets
        ├── css/
        │   └── style.css          # Main stylesheet (dark theme)
        ├── js/
        │   ├── socket.js          # WebSocket client
        │   ├── map.js             # Leaflet map functions
        │   └── chat.js            # Chat functionality
        └── images/
            └── ...                # Logos, icons, etc.
```

### Database Schema

```sql
-- Users Table
CREATE TABLE user (
    id INTEGER PRIMARY KEY,
    name VARCHAR,
    email VARCHAR UNIQUE,
    phone VARCHAR,
    password_hash VARCHAR,
    created_at TIMESTAMP
);

-- Rides Table
CREATE TABLE ride (
    id INTEGER PRIMARY KEY,
    driver_id INTEGER FOREIGN KEY,
    origin VARCHAR,
    destination VARCHAR,
    departure_time TIMESTAMP,
    available_seats INTEGER,
    status VARCHAR,  -- offered, completed, cancelled
    created_at TIMESTAMP
);

-- Ride Requests Table
CREATE TABLE ride_request (
    id INTEGER PRIMARY KEY,
    ride_id INTEGER FOREIGN KEY,
    passenger_id INTEGER FOREIGN KEY,
    status VARCHAR,  -- pending, accepted, rejected
    created_at TIMESTAMP
);

-- Chat Messages Table
CREATE TABLE message (
    id INTEGER PRIMARY KEY,
    ride_id INTEGER FOREIGN KEY,
    sender_id INTEGER FOREIGN KEY,
    content TEXT,
    timestamp TIMESTAMP
);
```

---

## 🚀 Deployment Guide

### Local Development (Already Covered Above)

### Render.com Deployment

UniHop is pre-configured for easy deployment on Render.com's free tier:

**Step 1: Prepare Your Repository**
```bash
git push origin main
```

**Step 2: Create Render Service**
- Go to [render.com](https://render.com)
- Click "New +" → "Web Service"
- Connect your GitHub repo
- Select the repository

**Step 3: Configure Build Settings**
- **Name**: unihop
- **Build Command**: `pip install -r requirements.txt`
- **Start Command**: `python app.py`
- **Runtime**: Python 3.11

**Step 4: Environment Variables**
Add in Render dashboard:
```
FLASK_ENV=production
SECRET_KEY=your-unique-secret-key-here
```

**Step 5: Deploy**
- Click "Create Web Service"
- Wait ~5 minutes for deployment
- Your app will be live at: `https://unihop.onrender.com`

**⚠️ Important Notes:**
- Render's free tier has an ephemeral file system
- SQLite database resets on app restart
- **For production**: Use PostgreSQL instead of SQLite
- Set `SQLALCHEMY_DATABASE_URI` environment variable:
  ```
  postgresql://username:password@host/dbname
  ```

---

## 🎨 Customization Guide

### Change Map Location

Edit `templates/map.html`:

```javascript
// Update center coordinates (example: University of Delhi)
const map = L.map('map').setView([28.5721, 77.2157], 13);

// Update campus boundaries
const bounds = L.latLngBounds(
    L.latLng(28.5600, 77.2000),  // Southwest
    L.latLng(28.5850, 77.2300)   // Northeast
);
map.fitBounds(bounds);
```

### Add Campus Locations

Edit `templates/map.html` - `locations` object:

```javascript
const locations = {
    'Main Gate': [28.5721, 77.2157],
    'Central Library': [28.5730, 77.2165],
    'Cafeteria': [28.5710, 77.2150],
    'Sports Complex': [28.5690, 77.2180],
    'Your Building': [YOUR_LAT, YOUR_LONG]
};
```

### Change Theme Colors

Edit `static/css/style.css`:

```css
:root {
    --primary: #6366f1;        /* Indigo */
    --secondary: #ec4899;      /* Pink */
    --background: #0f172a;     /* Dark blue */
    --surface: #1e293b;        /* Slate */
    --text-primary: #f1f5f9;   /* Light */
    --text-secondary: #cbd5e1; /* Gray */
}
```

### Update Security Key

**Critical for production!** Edit `app.py`:

```python
app.config['SECRET_KEY'] = 'your-unique-random-secret-key-here'
# Generate a strong key:
# python -c "import secrets; print(secrets.token_hex(32))"
```

---

## 🔧 Advanced Features & Enhancements

### 1. Machine Learning Ride Matching
```bash
pip install scikit-learn numpy
```

Implement intelligent ride matching based on:
- Route similarity (ML clustering)
- Time preferences
- User ratings
- Historical data

### 2. Email Notifications

```python
from flask_mail import Mail, Message

mail = Mail(app)

# Send email when ride is accepted
def send_ride_acceptance_email(passenger_email, ride_details):
    msg = Message(
        'Your Ride Request Accepted!',
        recipients=[passenger_email]
    )
    msg.body = f"Your request for {ride_details} has been accepted."
    mail.send(msg)
```

### 3. Reviews & Ratings System

```python
class Rating(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    from_user_id = db.Column(db.Integer, db.ForeignKey('user.id'))
    to_user_id = db.Column(db.Integer, db.ForeignKey('user.id'))
    rating = db.Column(db.Integer)  # 1-5
    comment = db.Column(db.Text)
    created_at = db.Column(db.DateTime, default=datetime.utcnow)
```

### 4. Payment Integration

```python
# Razorpay integration example
from razorpay import Client

razorpay_client = Client(
    auth=('key_id', 'key_secret')
)

payment_order = razorpay_client.order.create({
    'amount': int(fare * 100),  # Amount in paise
    'currency': 'INR',
    'receipt': f'ride_{ride_id}'
})
```

### 5. Real-Time Location Tracking

```python
# Update driver location in real-time
@socketio.on('update_location')
def update_driver_location(data):
    driver_id = data['driver_id']
    latitude = data['latitude']
    longitude = data['longitude']
    
    emit('driver_location_updated', {
        'driver_id': driver_id,
        'lat': latitude,
        'lng': longitude
    }, broadcast=True)
```

### 6. File Sharing in Chat

```python
@socketio.on('send_image')
def send_image(data):
    message = Message(
        ride_id=data['ride_id'],
        sender_id=data['sender_id'],
        content=data['image_base64'],
        message_type='image'
    )
    db.session.add(message)
    db.session.commit()
    
    emit('new_message', format_message(message), broadcast=True)
```

---

## 🐛 Troubleshooting

### ❌ Issue: Port 5000 Already in Use

**Solution:**
```bash
# Change port in app.py
if __name__ == "__main__":
    socketio.run(app, host="0.0.0.0", port=5001, debug=True)
```

Or kill the process:
```bash
# macOS/Linux
lsof -ti:5000 | xargs kill -9

# Windows
netstat -ano | findstr :5000
taskkill /PID <PID> /F
```

### ❌ Issue: ModuleNotFoundError

**Solution:**
```bash
# Verify virtual environment is activated
source venv/bin/activate  # macOS/Linux
venv\Scripts\activate     # Windows

# Reinstall all dependencies
pip install -r requirements.txt --force-reinstall
```

### ❌ Issue: Database Locked

**Solution:**
```bash
# Delete the database and restart
rm carpooling.db
python app.py
# Fresh database will be created automatically
```

### ❌ Issue: WebSocket Connection Failed

**Cause:** Flask-SocketIO might not be installed or app.py configuration issue

**Solution:**
```bash
pip install flask-socketio python-socketio python-engineio
pip install -U --force-reinstall flask-socketio
```

### ❌ Issue: Map Not Loading

**Solution:** Check browser console (F12) for errors. Verify:
- Internet connection (OpenStreetMap tiles need it)
- Browser allows location access
- Leaflet.js CDN is accessible

---

## 📚 Learning Resources

| Resource | URL |
|----------|-----|
| **Flask Docs** | https://flask.palletsprojects.com/ |
| **Flask-SocketIO** | https://flask-socketio.readthedocs.io/ |
| **SQLAlchemy ORM** | https://docs.sqlalchemy.org/ |
| **Leaflet.js** | https://leafletjs.com/reference.html |
| **OpenStreetMap** | https://www.openstreetmap.org/ |
| **HTML/CSS/JS** | https://developer.mozilla.org/ |
| **WebSockets** | https://developer.mozilla.org/en-US/docs/Web/API/WebSocket |

---

## 🔐 Security Best Practices

⚠️ **This project is for learning purposes. Before production deployment:**

- ✅ Use environment variables for all secrets (`.env` file with `python-dotenv`)
- ✅ Implement CSRF protection (`Flask-WTF`)
- ✅ Use HTTPS/SSL certificates (Let's Encrypt)
- ✅ Add rate limiting to prevent abuse
- ✅ Implement input validation & sanitization
- ✅ Add CORS protection
- ✅ Use secure password hashing (bcrypt/argon2)
- ✅ Implement proper error handling (don't leak stack traces)
- ✅ Add SQL injection prevention (SQLAlchemy parameterized queries)
- ✅ Regular security audits

---

## 📊 Future Roadmap

- [ ] **Mobile Apps** (React Native/Flutter)
- [ ] **Social Features** (Friend groups, team rides)
- [ ] **Schedule Planning** (Recurring rides)
- [ ] **Payment Integration** (Razorpay/Stripe)
- [ ] **AI-Powered Recommendations** (Route optimization)
- [ ] **Accessibility Features** (Screen reader support)
- [ ] **Multi-language Support** (i18n)
- [ ] **Admin Dashboard** (Moderation & analytics)
- [ ] **API Documentation** (Swagger/OpenAPI)
- [ ] **Comprehensive Tests** (Unit & integration tests)

---

## 🤝 Contributing

We welcome contributions! Here's how:

1. **Fork** the repository
2. **Create feature branch** (`git checkout -b feature/amazing-feature`)
3. **Commit changes** (`git commit -m 'Add amazing feature'`)
4. **Push to branch** (`git push origin feature/amazing-feature`)
5. **Open Pull Request** with detailed description

### Contribution Ideas:
- Add missing features from roadmap
- Improve UI/UX
- Write comprehensive tests
- Optimize performance
- Add documentation
- Fix bugs & issues

---

## 📄 License

This project is licensed under the **Eclipse Public License 2.0** (EPL 2.0) - see the [LICENSE](https://github.com/Vikranth-patel/UNIHOP./blob/main/LICENSE) file for details.

---

## 👨‍💻 Credits & Author

**Created by:** Vikranth Patel  
**Learning Project:** First-year CSE Student  
**University:** DU (Delhi University)  

This project demonstrates practical implementation of:
- Full-stack web development
- Real-time communication systems
- Database design & management
- RESTful API design
- Frontend responsive design

---

## 📞 Support & Contact

- **GitHub Issues**: [Report bugs or request features](https://github.com/Vikranth-patel/UNIHOP./issues)
- **GitHub Discussions**: [Ask questions & ideas](https://github.com/Vikranth-patel/UNIHOP./discussions)
- **Email**: [vikranthpatel16@gmail.com](mailto:vikranthpatel16@gmail.com)

---

## 📈 Project Stats

- **Language**: HTML (Primary for deployment)
- **Framework**: Flask (Python)
- **Real-Time**: WebSockets (SocketIO)
- **Database**: SQLite
- **License**: EPL 2.0
- **Status**: 🟢 Active Development
- **Created**: February 2026

---

## 🎓 Learning Outcomes

This project teaches:
- ✓ Full-stack web development
- ✓ Real-time communication protocols
- ✓ Database design & ORM usage
- ✓ Responsive UI/UX design
- ✓ Security best practices
- ✓ Deployment & DevOps basics
- ✓ Collaborative development with Git

---

**Happy Carpooling! 🚗💨**  
*Connect. Share. Save. Hop In!*

---

**Last Updated:** June 2026  
**Version:** 1.0.0 (MVP)  
**Status:** ✅ Stable & Production-Ready
