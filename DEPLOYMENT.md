# Deployment Guide for Student Performance Dashboard

Your dashboard is configured to deploy to any cloud platform with zero configuration issues.

---

## Option 1: Deploy for FREE on Render (Recommended)

1. Push this repository to **GitHub**.
2. Go to [https://render.com](https://render.com) and sign in.
3. Click **New +** → **Web Service**.
4. Select your GitHub repository.
5. Set the settings:
   - **Environment**: `Python 3`
   - **Build Command**: `pip install -r student_dashboard/requirements.txt`
   - **Start Command**: `cd student_dashboard && gunicorn app:app`
6. Click **Deploy Web Service**!
7. *Optional MongoDB Atlas connection*: Under Environment Variables, add `MONGO_URI` with your MongoDB Atlas connection string. (If you don't add one, the dashboard automatically runs with in-memory sample students so it **never crashes**!).

---

## Option 2: Deploy on Railway

1. Go to [https://railway.app](https://railway.app).
2. Click **New Project** → **Deploy from GitHub repo**.
3. Railway automatically detects `requirements.txt` and `Procfile`.
4. Click Deploy!

---

## Option 3: Deploy on PythonAnywhere

1. Upload files to PythonAnywhere.
2. In the **Web** tab, create a new manual Python 3.11 web app.
3. Set your WSGI file to import `app` from `app.py`:
   ```python
   import sys
   path = '/home/yourusername/student_dashboard/student_dashboard'
   if path not in sys.path:
       sys.path.append(path)
   from app import app as application
   ```
4. Reload the web app.

---

## Option 4: Open via VS Code "Go Live" (Instant Local Preview)

1. Right-click on `index.html`.
2. Click **Open with Live Server**.
3. The dashboard opens at `http://127.0.0.1:5500/index.html` with full working charts, table filters, risk radar, and score prediction!

---

## Default Admin Credentials
- **Username**: `admin`
- **Password**: `admin123`
- **Forgot Password Mobile**: `+918600731792`
