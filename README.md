
# ✈️ Airline Passenger Satisfaction Predictor

Welcome to the **Airline Satisfaction Predictor** – a machine learning web application that predicts whether a passenger is **satisfied** or **dissatisfied** based on various travel attributes. It supports both **individual predictions via a form** and **batch predictions via Excel upload**.

🔗 **Live App**: [Coming Soon or Add your link here]  
📁 **Colab Notebook**: [Airline Passenger Satisfaction Prediction ](https://colab.research.google.com/drive/1-i8CzEX2--OhfTApecdQM1eQJhFXiyiD?usp=sharing)

---

## 🚀 Features

- 🧠 Predict satisfaction based on ML model (Random Forest)
- 📄 Upload Excel sheets for batch prediction
- 🖥️ Clean and interactive frontend using HTML, CSS & JavaScript
- 📦 Model trained on airline customer dataset
- 📉 Download predictions as Excel output
- 🧰 Backend using Python (Flask) and `pickle` model loading

---

## 📊 Dataset Overview

The dataset includes 100K+ rows about airline passengers' experiences, such as:

- Flight Distance  
- Inflight Service Ratings  
- Seat Comfort  
- Food & Drink  
- Baggage Handling  
- Type of Travel (Personal/Business)  
- Class (Economy/Business/First)

---

## 🔧 Technologies Used

| Part         | Technology         |
|--------------|--------------------|
| Frontend     | HTML, CSS, JavaScript |
| Backend      | Flask (Python)     |
| ML Model     | RandomForestClassifier (`scikit-learn`) |
| Data Handling| pandas, numpy      |
| Deployment   | Netlify (Frontend), Render/Local (Flask API) |
| File Format  | `.xlsx` (Excel)    |

---

## 📂 Project Structure

```

airline-satisfaction-predictor/
├── static/
│   └── style.css                # Frontend CSS
├── templates/
│   ├── index.html               # Home page with prediction form
│   └── result.html              # Output display
├── DMBI\_CA2.ipynb               # ML training & EDA notebook
├── final\_random\_forest\_model.pkl # Trained model file
├── app.py                       # Flask backend
├── requirements.txt             # Python dependencies
└── README.md                    # Project documentation

````

---

## 🛠️ Installation & Running Locally

### Prerequisites

- Python 3.9+
- pip
- Flask

### Setup

1. Clone the repo:

```bash
git clone https://github.com/atharvnikam38/airline-satisfaction-predictor.git
cd airline-satisfaction-predictor
````

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Run the Flask App:

```bash
python app.py
```

4. Open your browser and go to: `http://localhost:5000`

---

## 🧪 How It Works

1. **Single Prediction**: Fill out the form with travel details.
2. **Batch Prediction**: Upload an `.xlsx` file with multiple passenger records.
3. **Model Processing**: Flask loads `final_random_forest_model.pkl` and returns predictions.
4. **Output**: Displayed on-screen or downloadable as Excel file.

---


## 📌 Future Improvements

* Add user authentication
* Improve UI/UX using React or Bootstrap
* Enable cloud storage for uploaded files
* Include more ML models and comparisons
* Make app mobile responsive

---

## 🙋‍♂️ Author

**Atharv Nikam**
IT Student | Passionate about AI/ML, Web Dev & Open Source
🔗 [LinkedIn](https://www.linkedin.com/in/atharvnikam38) | 📧 [atharvnikam38@gmail.com](mailto:atharvnikam38@gmail.com)

---



