Here’s your complete **README.md** file content ready to use. Just copy and paste it into a file named `README.md` in your project root:

````markdown
# 📢 Promotions Module – Vedeshi Khana

This module powers the promotional features of **Vedeshi Khana**, allowing administrators to create, manage, and schedule offers to enhance user engagement and boost sales.

---

## 🚀 Features

- Create promotional campaigns with titles, descriptions, and images
- Apply discounts as fixed amounts or percentages
- Set promotion start and end dates
- Target specific items, categories, or customer groups
- Display promotional banners on the homepage, menu, or checkout
- Toggle activation status for quick control

---

## 🛠️ Tech Stack

- Frontend: Vue.js v3.2.1 (Admin & Customer Panels)
- Backend: Node.js + Express.js
- Database: MySQL (via XAMPP)
- SMS Integration: Twilio API

---

## 🔄 API Endpoints (Sample)

| Method | Endpoint             | Description                |
|--------|----------------------|----------------------------|
| GET    | `/api/promotions`    | List all promotions        |
| POST   | `/api/promotions`    | Create a new promotion     |
| PUT    | `/api/promotions/:id`| Update a promotion         |
| DELETE | `/api/promotions/:id`| Delete a promotion         |

---

## 📋 Setup & Installation Guide

### 1. Prerequisites

- [Node.js](https://nodejs.org/) (v14 or newer)
- npm (comes with Node.js)
- [XAMPP](https://www.apachefriends.org/index.html) for MySQL
- Twilio account with Account SID, Auth Token, and Phone Number

---

### 2. Database Setup

- Start **XAMPP** and run **Apache** and **MySQL**.
- Open phpMyAdmin (`http://localhost/phpmyadmin`).
- Create new database:

```sql
CREATE DATABASE bugrestaurant;
````

* Import your tables or create manually if needed.

---

### 3. Backend Setup

* Navigate to backend folder:

```bash
cd backend
```

* Install dependencies:

```bash
npm install
```

* Create a `.env` file in the backend folder:

```env
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_mysql_password
DB_NAME=bug_restaurant

PORT=3000

TWILIO_ACCOUNT_SID=your_twilio_account_sid
TWILIO_AUTH_TOKEN=your_twilio_auth_token
TWILIO_PHONE_NUMBER=your_twilio_phone_number
```

* Make sure your backend loads `.env` variables (using `dotenv` package).

* Example MySQL connection setup in backend:

```js
require('dotenv').config();
const mysql = require('mysql');

const connection = mysql.createConnection({
  host: process.env.DB_HOST,
  user: process.env.DB_USER,
  password: process.env.DB_PASSWORD,
  database: process.env.DB_NAME
});

connection.connect(err => {
  if (err) {
    console.error('DB connection error:', err);
    return;
  }
  console.log('Connected to MySQL database');
});
```

* Start backend server:

```bash
npm start
```

---

### 4. Frontend Setup

* Navigate to frontend folder:

```bash
cd ../frontend
```

* Install dependencies (Vue.js v3.2.1 is in `package.json`):

```bash
npm install
```

* Run frontend development server:

```bash
npm run serve
```

* Build frontend for production:

```bash
npm run build
```

---

### 5. SMS (Twilio) Integration Example

* Install Twilio SDK:

```bash
npm install twilio
```

* Example Twilio SMS sending function in backend:

```js
const twilio = require('twilio');
const client = new twilio(process.env.TWILIO_ACCOUNT_SID, process.env.TWILIO_AUTH_TOKEN);

function sendSms(to, message) {
  client.messages
    .create({
      body: message,
      from: process.env.TWILIO_PHONE_NUMBER,
      to: to
    })
    .then(msg => console.log('SMS sent:', msg.sid))
    .catch(err => console.error('SMS error:', err));
}
```

---

### 6. Common Commands

| Action                        | Command                                     | Location                  |
| ----------------------------- | ------------------------------------------- | ------------------------- |
| Install backend packages      | `npm install`                               | `/backend`                |
| Start backend server          | `npm start` or `npm run dev`                | `/backend`                |
| Install frontend packages     | `npm install`                               | `/frontend`               |
| Start frontend dev server     | `npm run serve`                             | `/frontend`               |
| Build frontend for production | `npm run build`                             | `/frontend`               |
| Reinstall node\_modules       | Delete `node_modules` and run `npm install` | `/backend` or `/frontend` |

---

### 7. Tips & Troubleshooting

* Restart backend server after `.env` changes.
* Use `nodemon` for auto-restart during development (`npm install -g nodemon`).
* Ensure MySQL service is running before backend start.
* Commit `package.json` and `package-lock.json` to GitHub, **do not commit your `.env` file**.
* Run `npm install` if modules are missing or after deleting `node_modules`.

---

## 👥 Authors

**Vishal Suthar**
Email: [vishalsuthar2002@outlook.com](mailto:vishalsuthar2002@outlook.com)
GitHub: [BUGzz007](https://github.com/BUGzz007)



---

## ⚖️ License

© 2025 Vedeshi Khana. All rights reserved.

