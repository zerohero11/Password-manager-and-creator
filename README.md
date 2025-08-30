# 🔐 Password Manager & Creator

A full-stack web application for securely managing and generating passwords. Built with React.js frontend and Node.js backend, featuring a modern dark theme with video background.

![Password Manager](https://img.shields.io/badge/Status-Active-green)
![React](https://img.shields.io/badge/React-18.3.1-blue)
![Node.js](https://img.shields.io/badge/Node.js-Express-green)
![MySQL](https://img.shields.io/badge/Database-MySQL-orange)

## ✨ Features

### 🔑 Password Management
- **Add Passwords**: Store passwords with custom titles/descriptions
- **View Saved Passwords**: Display all your stored passwords in an organized list
- **Delete Passwords**: Remove passwords with confirmation dialog
- **User Authentication**: Secure login and signup system

### 🎲 Password Generator
- **Customizable Length**: Generate passwords from 8-40 characters
- **Character Options**: Include/exclude numbers and special characters
- **Smart Generation**: Ensures required character types are included
- **Copy to Clipboard**: One-click copy functionality
- **Live Preview**: Real-time password generation as you adjust settings

### 🎨 User Interface
- **Modern Design**: Clean, intuitive interface with dark theme
- **Video Background**: Dynamic background video for visual appeal
- **Responsive Layout**: Works on various screen sizes
- **Navigation**: Seamless routing between different sections
- **User Feedback**: Success/error messages for all actions

## 🛠️ Technology Stack

### Frontend
- **React.js** (18.3.1) - User interface library
- **React Router DOM** - Client-side routing
- **Axios** - HTTP client for API requests
- **CSS3** - Styling and animations

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web application framework
- **MySQL2** - Database driver with promise support
- **CORS** - Cross-origin resource sharing
- **UUID** - Unique identifier generation

### Database
- **MySQL** - Relational database management system

## 📁 Project Structure

```
Password-manager-and-creator/
├── client/                     # React frontend
│   ├── public/
│   │   ├── websiteBackground.mp4
│   │   └── ...
│   ├── src/
│   │   ├── App.js             # Main application component
│   │   ├── login.js           # Authentication component
│   │   ├── PasswordGenerator.js # Password generation
│   │   ├── ShowSavedPasswords.js # Password display
│   │   └── *.css              # Styling files
│   └── package.json
├── server/                     # Node.js backend
│   ├── index.js               # Express server and API routes
│   ├── db.js                  # Database configuration
│   └── package.json
└── README.md
```

## 🚀 Quick Start

### Prerequisites
- **Node.js** (v14 or higher)
- **npm** or **yarn**
- **MySQL** (v8.0 or higher)

### 1. Clone the Repository
```bash
git clone https://github.com/zerohero11/Password-manager-and-creator.git
cd Password-manager-and-creator
```

### 2. Database Setup
Create a MySQL database and tables:

```sql
-- Create database
CREATE DATABASE PasswordManager;
USE PasswordManager;

-- Create users table
CREATE TABLE users (
    userID VARCHAR(255) PRIMARY KEY,
    entryPass VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Create passwords table
CREATE TABLE passwords (
    ID INT AUTO_INCREMENT PRIMARY KEY,
    password VARCHAR(255) NOT NULL,
    title VARCHAR(255) NOT NULL,
    userID VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (userID) REFERENCES users(userID) ON DELETE CASCADE
);
```

### 3. Backend Setup
```bash
cd server
npm install
```

Update database credentials in `server/index.js`:
```javascript
const pool = mysql.createPool({
  host: 'localhost',
  user: 'your_mysql_username',     // Update this
  password: 'your_mysql_password', // Update this
  database: 'PasswordManager',
  // ... other settings
});
```

Start the backend server:
```bash
npm start
# or
node index.js
```
Server will run on `http://localhost:3001`

### 4. Frontend Setup
```bash
cd ../client
npm install
npm start
```
Application will open at `http://localhost:3000`

## 🔧 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/login` | User authentication |
| POST | `/signup` | User registration |
| POST | `/addpassword` | Store new password |
| GET | `/passwords/:userID` | Retrieve user's passwords |
| DELETE | `/deletepassword/:id` | Delete specific password |

## 🎯 Usage

### Getting Started
1. **Sign Up**: Create a new account with username and password
2. **Log In**: Access your account using your credentials
3. **Add Passwords**: Store passwords with descriptive titles
4. **Generate Passwords**: Create strong, secure passwords
5. **Manage Passwords**: View, copy, or delete stored passwords

### Password Generator Options
- **Length Slider**: Adjust password length (8-40 characters)
- **Numbers Checkbox**: Include numeric characters (0-9)
- **Special Characters**: Include symbols (!@#$%^&*)
- **Copy Button**: Copy generated password to clipboard

## ⚠️ Security Considerations

> **Important**: This is a demonstration project and should not be used for storing real passwords without implementing proper security measures.

### Current Limitations
- Passwords are stored in **plain text** (major security risk)
- No password hashing or encryption
- Basic authentication without JWT tokens
- No HTTPS implementation

### Recommended Improvements
- Implement password hashing (bcrypt)
- Add encryption for stored passwords
- Use JWT for authentication
- Implement HTTPS
- Add input validation and sanitization
- Implement rate limiting
- Add password strength validation

## 🚧 Development

### Running in Development
```bash
# Backend (Terminal 1)
cd server
npm start

# Frontend (Terminal 2)
cd client
npm start
```

### Environment Variables
Create a `.env` file in the server directory:
```env
DB_HOST=localhost
DB_USER=your_username
DB_PASSWORD=your_password
DB_NAME=PasswordManager
PORT=3001
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built with modern web technologies
- Inspired by the need for secure password management
- Educational project for learning full-stack development

## 📞 Contact

**GitHub**: [@zerohero11](https://github.com/zerohero11)
**Repository**: [Password-manager-and-creator](https://github.com/zerohero11/Password-manager-and-creator)

---

⭐ **Star this repository if you found it helpful!**
