Car Rental Feedback Analyzer (Watson AI) 🚗

A Streamlit web app that uses IBM Watson Natural Language Understanding (NLU) to analyze customer reviews, detect overall sentiment, and highlight common issues.

📂 Project Structure
car_rental_feedback_analyzer/
├── app.py                     # Main Streamlit application
├── requirements.txt           # Python dependencies
├── README.md                  # This file
└── .streamlit/
    └── secrets_template.toml  # Rename to secrets.toml & add Watson creds
🔧 Prerequisites
Python 3.9+ installed
An IBM Cloud account
A Natural Language Understanding service instance
Your service API key and URL
⚙️ Setup
# Clone / unzip the project
cd car_rental_feedback_analyzer

# Create a virtual environment (optional but recommended)
python -m venv .venv
source .venv/bin/activate   # On Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
Configure Watson Credentials
Rename the secrets template and paste your credentials:

mv .streamlit/secrets_template.toml .streamlit/secrets.toml
Edit .streamlit/secrets.toml:

[default]
WATSON_API_KEY   = "xxxxxxxxxxxxxxxxxxxxxxxxxxxx"
WATSON_SERVICE_URL = "https://api.us-south.natural-language-understanding.watson.cloud.ibm.com/instances/xxxxx"
Tip: You can find the key & URL in IBM Cloud Console → your NLU service → Manage → API Keys & Endpoints. citeturn0search3

🚀 Run the App
streamlit run app.py
Open the local URL shown in your terminal (default: http://localhost:8501).
Upload a CSV (review, optional rating) or tick Use demo data to test.

📝 Using Watsonx.ai Studio (Optional)
If you prefer IBM watsonx.ai Studio:

Create / open a project in watsonx.ai.
Add a Python environment & copy the repo files.
Add the Natural Language Understanding service to your project (Services → Add service instance).
In Manage → Service credentials, copy API Key & URL and export them as env variables or keep them in secrets.toml.
From a Terminal in watsonx.ai, run:
pip install -r requirements.txt
streamlit run --server.port 8080 app.py
Expose port 8080 via the Expose App button to access the UI.
