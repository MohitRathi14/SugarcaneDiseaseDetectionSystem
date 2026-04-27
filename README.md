# Sugarcane Disease Detection

A multi-service project for detecting sugarcane leaf disease using an image classification model, a Python API, a Node.js backend, and a React frontend.

## Project Overview

- `app.py`: Root FastAPI application that exposes a prediction endpoint and loads the ML model from `predict.py`.
- `predict.py`: Loads the trained TensorFlow model from `ml-service/model/sugarcane_model_final.keras` and class names from `ml-service/model/class_names.json`.
- `backend/`: Node.js/Express backend for file uploads, Cloudinary integration, and prediction request orchestration.
- `frontend/`: React + Vite frontend for uploading images and viewing prediction results.
- `ml-service/`: Contains the dataset folders and trained model artifacts.

## Repository Structure

- `app.py` - FastAPI application for image URL prediction.
- `predict.py` - ML inference helper that returns disease predictions.
- `backend/` - Express server and Cloudinary upload logic.
- `frontend/` - Vite React app for the user interface.
- `ml-service/model/` - Trained model and class labels.
- `Image/` - Example image files for testing.

## Requirements

### Python

The root Python service requires:

- Python 3.10+ (or compatible)
- `fastapi`
- `uvicorn`
- `tensorflow`
- `numpy`
- `requests`
- `pydantic`

### Node.js / Backend

The backend service uses:

- `express`
- `cors`
- `dotenv`
- `cloudinary`
- `multer`
- `multer-storage-cloudinary`
- `axios`
- `mongoose`

### Frontend

The frontend uses:

- React
- Vite
- Tailwind CSS
- Axios
- React Router
- Framer Motion
- Recharts

## Setup and Run

### Python API

1. Create and activate a Python environment.
2. Install dependencies:
   ```bash
   pip install fastapi uvicorn tensorflow numpy requests pydantic
   ```
3. Run the API:
   ```bash
   uvicorn app:app --reload --host 0.0.0.0 --port 8000
   ```
4. Health check:
   ```http
   GET http://localhost:8000/
   ```

### Node.js Backend

1. Navigate to the backend folder:
   ```bash
   cd backend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the server:
   ```bash
   node index.js
   ```

### Frontend

1. Navigate to the frontend folder:
   ```bash
   cd frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the app:
   ```bash
   npm run dev
   ```

## Prediction Endpoints

- `POST /predict-url` - Accepts JSON with `image_url` and returns prediction results.
- The root app currently includes a commented-out file upload route for future support.

## Notes

- The model input size is `299x299` and the inference pipeline uses raw pixel data.
- `ml-service/model/class_names.json` defines the disease categories.
- If you add environment variables, store them in a `.env` file and load them in the backend using `dotenv`.

## License

This repository does not currently specify a license.
