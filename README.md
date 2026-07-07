# DT-Project

A Flask-based student management and study resource platform that enables students to connect, collaborate, and find study resources based on their year and subject.

## 🎯 Features

- **User Authentication**: Secure login and registration system
- **Student Profiles**: Create and manage student profiles with year and subject information
- **Study Resource Discovery**: Find study partners based on shared subjects and academic year
- **Profile Management**: Update profile information or delete accounts
- **Chat System**: Built-in messaging system for student communication
- **Responsive Web Interface**: HTML and CSS-based frontend

## 🛠️ Tech Stack

- **Backend**: Python 3 with Flask web framework
- **Database**: MySQL
- **Frontend**: HTML, CSS
- **Server**: Gunicorn (for production deployment)

## 📊 Project Composition

- CSS: 43.8%
- HTML: 43%
- Python: 13.2%

## 📁 Project Structure

```
DT-project/
├── main.py                    # Flask application entry point
├── requirements.txt           # Python dependencies
├── templates/                 # HTML templates directory
│   ├── Login.html
│   ├── Registration.html
│   ├── profile.html
│   ├── update_profile.html
│   ├── Study.html
│   ├── search_result.html
│   ├── Webpage.html
│   ├── chatting.html
│   ├── contact.html
│   └── about.html
├── static/                    # Static assets (CSS, images, JS)
├── Assets/                    # Project assets
└── addingcontent_web.html     # Additional web content template
```

## 🚀 Getting Started

### Prerequisites

- Python 3.x
- MySQL Server
- pip (Python package manager)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Yadavsandeep-stack/DT-project.git
   cd DT-project
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure database connection**
   
   Update the database credentials in `main.py`:
   ```python
   db = mysql.connector.connect(
       host="your_host",
       user="your_user",
       password="your_password",
       database="your_database",
       port="your_port"
   )
   ```

5. **Create database tables**
   
   Execute the following SQL commands in your MySQL database:
   ```sql
   CREATE TABLE student (
       username VARCHAR(255) PRIMARY KEY,
       email VARCHAR(255) UNIQUE,
       password VARCHAR(255),
       year VARCHAR(50),
       subject VARCHAR(255)
   );
   
   CREATE TABLE subjects_table (
       id INT AUTO_INCREMENT PRIMARY KEY,
       subject VARCHAR(255)
   );
   
   CREATE TABLE year_table (
       id INT AUTO_INCREMENT PRIMARY KEY,
       year VARCHAR(50)
   );
   ```

6. **Run the application**
   ```bash
   python main.py
   ```

   The application will be available at `http://localhost:5000`

## 📝 API Routes

| Route | Method | Description |
|-------|--------|-------------|
| `/` | GET | Home page / Login page |
| `/login` | POST | User login |
| `/register` | GET, POST | User registration |
| `/profile` | GET | View user profile |
| `/update_profile` | GET, POST | Update profile information |
| `/delete_profile` | POST | Delete user account |
| `/logout` | GET | User logout |
| `/homepage` | GET | Main webpage |
| `/study` | GET | Study resource search page |
| `/search_results` | GET | Display search results |
| `/contact` | GET | Contact page |
| `/about` | GET | About page |
| `/chatting` | GET | Chat interface |

## 🔐 Security Notes

⚠️ **Important**: The current implementation stores passwords in plain text. For production use:
- Implement password hashing using `werkzeug.security` or `bcrypt`
- Use environment variables for database credentials
- Implement CSRF protection
- Add input validation and sanitization

Example password hashing:
```python
from werkzeug.security import generate_password_hash, check_password_hash

hashed_password = generate_password_hash(password)
check_password_hash(hashed_password, password)
```

## 📦 Key Dependencies

- **Flask**: Web framework
- **mysql-connector-python**: MySQL database connector
- **Gunicorn**: WSGI HTTP server
- **spaCy**: Natural language processing
- **geopy**: Geocoding and distance calculations
- **googletrans**: Google Translate API
- **requests**: HTTP library

## 🐛 Known Issues & TODOs

- Password security needs to be improved with hashing
- Database credentials should be stored in environment variables
- Add form validation on both frontend and backend
- Implement proper error handling and logging
- Add CSRF protection to forms
- Consider implementing JWT for better session management

## 🤝 Contributing

Feel free to fork this repository and submit pull requests for any improvements.

## 📄 License

This project is open source and available under the MIT License.

## 👤 Author

[Yadavsandeep-stack](https://github.com/Yadavsandeep-stack)

---

**Last Updated**: April 2026

