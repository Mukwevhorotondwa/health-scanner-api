# Health Scan ZA API (Backend)

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?style=flat-square&logo=python)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-2.3-lightgrey?style=flat-square&logo=flask)](https://flask.palletsprojects.com/)
[![Render](https://img.shields.io/badge/Deployment-Render-success?style=flat-square&logo=render)](https://render.com/)

A secure, RESTful microservice built with **Flask** to calculate and serve health scores and nutritional data. This API supports the [Health Scan ZA Frontend Application](https://charming-unicorn-12345.netlify.app).

---

## 📂 Project Structure

The project follows a standard Python web service architecture.

---

## ⚙️ Key Technologies & Security

| Feature | Technologies | Purpose |
| :--- | :--- | :--- |
| **Framework** | `Flask` | Provides the lightweight web application structure. |
| **Security** | `Flask-CORS` | Restricts API access to the approved frontend domain. |
| **Security** | `Flask-Limiter` | Implements API **Rate Limiting** to prevent abuse. |
| **Database** | `sqlite3` | Used with **parameterized queries** to prevent SQL Injection. |
| **Deployment** | `Gunicorn`, `Render` | Production-ready web server and hosting platform. |

---

## 🛠️ Setup & Local Run

### Prerequisites
* Python 3.10+
* `pip`

### Setup Steps

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/YourUsername/health-scanner-api-repo.git](https://github.com/YourUsername/health-scanner-api-repo.git)
    cd health-scanner-api-repo
    ```
2.  **Setup Environment:**
    ```bash
    python -m venv venv
    source venv/bin/activate
    ```
3.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
4.  **Run the API:**
    ```bash
    python app.py
    # API available at [http://127.0.0.1:5000](http://127.0.0.1:5000)
    ```
    *Ensure `database.py` is run once to create the `products.db` file.*

---

## ☁️ Deployment

The service is deployed on **Render** using the following configuration defined in `Procfile`:

| Configuration | Value |
| :--- | :--- |
| **Start Command** | `gunicorn --bind 0.0.0.0:$PORT app:app` |
| **CORS Policy** | Defined in `app.py` and must be updated with the live Netlify Frontend URL. |

***