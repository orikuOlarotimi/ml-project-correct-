# 🌿 Plant Disease Detection – ML School Project

A machine learning web app that detects plant diseases from images using a pre-trained MobileNetV2 model. Upload a plant leaf image and the app returns the disease name, description, and recommended treatment steps.

---

## 📁 Project Structure

```
ml-project-correct-/
│
├── app.py                  # Flask web server & API routes
├── main.py                 # Entry point / app runner
├── prediction.py           # Image preprocessing & model inference
├── train_model.py          # Model training script (MobileNetV2)
├── plant_disease_model.h5  # Pre-trained Keras model
├── disease_info(1).csv     # Disease info database (name, description, steps)
├── requirements.txt        # Python dependencies
└── README.md
```

---

## ⚙️ Requirements

- Python **3.8 – 3.10** (recommended; TensorFlow has limited support above 3.10)
- pip (Python package manager)
- Git

---

## 🚀 Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/orikuOlarotimi/ml-project-correct-.git
cd ml-project-correct-
```

### 2. Create a Virtual Environment (Recommended)

This keeps your project dependencies isolated from the rest of your system.

**On macOS / Linux:**
```bash
python3 -m venv venv
source venv/bin/activate
```

**On Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

> You'll know it's active when you see `(venv)` at the start of your terminal line.

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

This will install:
| Package | Purpose |
|---|---|
| `flask` | Web server framework |
| `werkzeug` | Secure file handling |
| `tensorflow` | Loading and running the ML model |
| `numpy` | Image array processing |
| `pandas` | Reading the disease info CSV |

### 4. Make Sure the Model File Is Present

Ensure `plant_disease_model.h5` and `disease_info(1).csv` are in the root project folder. These are required for predictions to work.

---

## ▶️ Running the App

```bash
python app.py
```

The server will start on:

```
http://localhost:5000
```

You should see output like:
```
* Running on http://0.0.0.0:5000
* Debug mode: on
```

---

## 🧪 Using the API

Send a POST request to `/predict` with a plant leaf image.

**Using curl:**
```bash
curl -X POST http://localhost:5000/predict \
  -F "file=@your_leaf_image.jpg"
```

**Example Response:**
```json
{
  "disease_name": "Tomato Late Blight",
  "description": "A fungal disease caused by Phytophthora infestans.",
  "Possible Steps": "Remove infected leaves, apply fungicide, avoid overhead watering."
}
```

---

## 🛠️ Troubleshooting

| Problem | Fix |
|---|---|
| `ModuleNotFoundError` | Make sure your virtual environment is activated and you ran `pip install -r requirements.txt` |
| `model not found` error | Check that `plant_disease_model.h5` is in the project root |
| Port 5000 already in use | Change the port in `app.py`: `app.run(port=5001)` |
| TensorFlow install fails | Make sure you're using Python 3.8–3.10 |

---

## 📌 Notes

- The model was trained using **MobileNetV2** with transfer learning on a plant disease dataset.
- `train_model.py` contains the full training pipeline (currently commented out — the pre-trained `.h5` model is included so you don't need to retrain).
- Uploaded images are saved temporarily and deleted after prediction.
- please for this backend to work with the frontend use a server for hosting either a remote or use a local server like ngrok 

---

## 👤 Author

**Oriku Olarotimi**  
ML School Project – 2025/2026
