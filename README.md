# 🛒 My Grocery Store – Online Grocery Platform

**Developer:** Satvik Chandrakar  
**Roll No:** 21f1000344  
**Subject:** MAD-II Project

---

## 🧾 About the Project

**My Grocery Store** is a full-stack, multi-user web application that allows users to browse and purchase groceries from various categories. The platform includes admin and store manager features, supports role-based access control, and uses background jobs for reminders and reporting.

---

## 🛠️ Technologies Used

- **Backend API:** Flask  
- **Frontend:** Vue.js
- **Database:** SQLite3  
- **Styling:** Bootstrap  
- **Caching:** Redis  
- **Batch Jobs:** Redis + Celery

---

## 🌟 Features

### 1. 🔐 Signup & Login
- Token-based authentication via Flask Security.
- Role-based access: Admin, Store Manager, and User.
- Single admin user.
- Users can apply to open a store; approval required by admin.

### 2. 🗂️ Section/Category Management (Admin Only)
- Add, edit, and delete categories (with confirmation).
- Approve store manager requests to modify categories.

### 3. 📦 Product Management (Store Managers)
- Add, edit, and delete products.
- Request admin approval to manage categories.
- Products must be assigned to categories (one-to-many).

### 4. 🔍 Search Functionality
- Search by section/category, brand, product name, and price.

### 5. 🛒 Shopping Cart
- Add products from multiple categories.
- View and manage items in the cart.

### 6. 🧾 Purchase Flow
- Browse products by category.
- Purchase multiple items.
- Out-of-stock indicators.
- Cart summary with total transaction amount.

### 7. ⏰ Daily Reminder
- At 7:30 AM daily, sends reminders to users who didn’t make a purchase the previous day.

### 8. 📊 Monthly Activity Report
- Sends summary reports to all users on the 1st of each month.

### 9. 📥 Download Product Details
- Store managers can download product lists from their stores.

### 10. ⚡ Caching
- Redis used to cache frequently accessed data and improve API performance.

---

## 📁 Project Folder Structure

- main.py :- It contains the python code to start the application
- templates folder :- It contains the html file to be rendered to the user
- static folder :- It contains all the JavaScript files required for frontend
- instance folder :- It contains the sqlite3 database
- application folder :- It contains the python code for various API
- requirements.txt :- It contains the name of the packages to be downloaded
- README.md :- It contains the information about the project and steps to be followed to start the application

---

## 🧩 Data Models

- **User** – Stores user details and credentials.
- **Role** – Contains roles: Admin, Store Manager, User.
- **RoleUsers** – Maps users to their roles.
- **Category** – Product classification information.
- **Product** – Contains product details.
- **Cart** – Tracks products added to users' carts.
- **Store** – Information about each store.
- **Store_Application** – Applications from users to start a store.
- **Orders** – Tracks user orders and purchases.
- **Request** – Store manager requests for category changes.

---

## 🧪 How to Run

Open a terminal in the project root directory and run the following commands

1. Install virtualenv:
```
$ pip install virtualenv
```

2. Create virtual environment:
```
$ virtualenv env
```

3. Then run the command:
```
$ source env/bin/activate
```

4. Then install the dependencies:
```
$ (env) pip install -r requirements.txt
```

5. Finally start the web server:
```
$ (env) python app.py
```

To start backend jobs, run the following commands

1. Start redis server:
```
$ redis-sever
```

2. Start mailhog smtp server
```
$ ~/go/bin/MailHog
```

3. Start the celery
```
$ celery -A main:cel_app worker -l INFO
```

4. Start the celery beat
```
$ celery -A main:cel_app beat -l INFO
```
