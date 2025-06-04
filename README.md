# 🛡️ Insurance Premium Category Predictor

This is a full-stack machine learning web application that predicts **insurance premium categories** (e.g., Low, Medium, High) based on user-provided information such as age, weight, height, income, smoking status, city, and occupation.

- **Frontend**: [Streamlit](https://streamlit.io/)
- **Backend API**: [FastAPI](https://fastapi.tiangolo.com/), hosted on [Render](https://render.com)

---

## 📌 Features

- User-friendly interface for input
- Real-time prediction using a hosted ML model
- Lightweight, easy to deploy

---

## 🚀 How to Use

### 🔹 Frontend (Streamlit)

The Streamlit app (`app.py`) collects user inputs and sends them to the FastAPI backend for prediction.

**Steps to Run Locally:**

1. Navigate to the frontend folder:
    ```bash
    cd frontend
    ```

2. Install dependencies:
    ```bash
    pip install streamlit requests
    ```

3. Run the app:
    ```bash
    streamlit run app.py
    ```

4. Make sure to update the `API_URL` in `app.py` with your backend URL:
    ```python
    API_URL = "https://insurance-premium-prediction-app-ckvq.onrender.com/predict"
    ```

---

### 🔹 Backend (FastAPI)

The FastAPI server serves the ML model and exposes a `/predict` endpoint.

**Steps to Run Locally:**

1. Navigate to the backend folder:
    ```bash
    cd backend
    ```

2. Install backend dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Start the FastAPI server:
    ```bash
    uvicorn main:app --reload
    ```

4. Access the interactive API docs at:
    ```
    http://127.0.0.1:8000/docs
    ```

---

## 🌍 Deployment

### ✅ Backend on Render

1. Push your backend (including `main.py`, `model.pkl`, and `requirements.txt`) to GitHub.
2. Go to [Render](https://render.com), create a new **Web Service**.
3. Connect your GitHub repo and set:
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `uvicorn main:app --host 0.0.0.0 --port 10000`
4. After deployment, note the URL and update your frontend's `API_URL`.

---

## 🔄 API Details

**POST** `/predict`

- **Content-Type**: `application/json`
- **Request Example**:

```json
{
  "age": 30,
  "weight": 65.0,
  "height": 1.7,
  "income_lpa": 10.0,
  "smoker": false,
  "city": "Mumbai",
  "occupation": "private_job"
}

