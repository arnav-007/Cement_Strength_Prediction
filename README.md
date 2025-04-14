# 🧠 ML Model Training API with Flask

This project is a Flask-based REST API that allows users to trigger **model training** using files from a specified folder. The API supports file validation, training using `scikit-learn` models, and handles errors gracefully.

---

## 📁 Project Structure

```
├── app.py                       # Main Flask application
├── training.py                  # Training logic
├── training_validation.py       # File validation logic
├── Training_Batch_Files/        # Input data directory
├── templates/                   # HTML templates (if any)
├── requirements.txt             # Required dependencies
└── README.md                    # This file
```

---

## 🚀 Features

- ✅ Accepts JSON request with folder path
- ✅ Validates input files
- ✅ Trains multiple ML models (e.g., Linear Regression)
- ✅ Logs model performance with cross-validation
- ✅ Compatible with both Windows & macOS

---

## 📡 API Endpoint

### `POST /train`

**Request Body:**
```json
{
  "folderPath": "Training_Batch_Files"
}
```

**Response:**
- ✅ Success: `"Training completed successfully."`
- ❌ Error: `"Error occurred! <Exception Details>"`

---

## 🔧 How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/ml-training-api.git
cd ml-training-api
```

### 2. Create & Activate Virtual Environment
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the Flask Server
```bash
python app.py
```

Server will run on: `http://127.0.0.1:5001`

---

## 📬 Example Request Using cURL

```bash
curl --location 'http://127.0.0.1:5001/train' \
--header 'Content-Type: application/json' \
--data '{
  "folderPath": "Training_Batch_Files"
}'
```

---

## ⚠️ Common Issues

- **Mac Compatibility**: Use `n_jobs=1` for parallel training to avoid multiprocessing issues on macOS.
- **Path Errors**: Always use absolute paths or make sure your working directory is correct.
- **KeyError**: Ensure the JSON body has `"folderPath"` key.

---

## 🤖 Model Training Notes

- Uses `GridSearchCV` for hyperparameter tuning
- Trains models like Linear Regression
- Stores best model based on cross-validation score
- Future plan: add model persistence with `joblib` and prediction endpoint

---

## 📦 Requirements

- Flask
- pandas
- scikit-learn
- numpy
- flask-cors

You can install them with:

```bash
pip install -r requirements.txt
```

---

## 🙌 Contributions

Pull requests are welcome! Feel free to open issues or suggest improvements.

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---
