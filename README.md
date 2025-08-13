Crop Yield Prediction Web App
This is a simple machine learning web application built with Flask.
It takes agricultural input parameters (such as rainfall, pesticide usage, temperature, etc.), processes them using a pre-trained preprocessing pipeline, and predicts the crop yield using a Decision Tree Regressor model.

The frontend is built with HTML (index.html), while all model computation and predictions are done on the backend in Python using scikit-learn.

📦 Tech Stack
Backend Framework: Flask (Python)

Machine Learning: scikit-learn (DecisionTreeRegressor + preprocessing pipeline)

Numerical Computing: NumPy

Model Serialization: pickle

Frontend: HTML templates rendered via Flask (Jinja2)

⚙️ Installation & Setup
Clone the repository

bash
git clone <your_repo_link>
cd <your_repo_folder>
Install the required dependencies

bash
pip install flask scikit-learn numpy
Ensure that the following pickle model files are in the models/ folder:

dtr.pkl — the trained Decision Tree Regressor model

preprocessor.pkl — the preprocessing pipeline (e.g., OneHotEncoder, StandardScaler, etc.)

Run the Flask server

bash
python app.py
Open the app in your browser
Go to:

text
http://127.0.0.1:5000
🚀 How it Works
User visits the main page (index.html) and fills in:

Year

Average Rainfall (mm/year)

Pesticides (tonnes)

Average Temperature (°C)

Area

Item (Crop type)

The form sends the data to the /predict route via POST.

Flask takes the inputs and transforms them using the preprocessor loaded from preprocessor.pkl.

The transformed features are then passed to the Decision Tree Regressor model (dtr.pkl) for prediction.

The prediction is sent back to index.html and displayed to the user.

📌 File Structure
text
project/
│
├── app.py                 # Flask app - handles routing, model loading, predictions
├── templates/
│   └── index.html          # Frontend HTML template
├── models/
│   ├── dtr.pkl            # Trained Decision Tree Regressor
│   └── preprocessor.pkl   # Preprocessing pipeline
└── README.md              # Project documentation
🛠 Dependencies
Make sure you have Python 3.7+ and install:

bash
pip install flask scikit-learn numpy
