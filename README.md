---

# 🛡️ UrbanIoT Threat Intelligence & Safety Monitor

**An AI-powered Decision Intelligence Platform designed for privacy-preserving smart city monitoring and rapid threat response.** Built for the **GenAI APAC Edition Academy Hackathon (Track 1)**, this platform bridges traditional Deep Learning (for pattern recognition) with modern Large Language Models (for cognitive translation). It analyzes real-time structural and environmental metadata to detect security anomalies, translating complex data spikes into plain-English, actionable protocols for city stakeholders.

# 🚀 The Problem It Solves

Modern smart cities generate massive amounts of infrastructure telemetry. Monitoring this manually is a bottleneck, but inspecting deep-packet data or video feeds violates citizen privacy.

This engine solves both by monitoring **pure metadata** (vibration, noise, crowd density flows). It utilizes an LSTM neural network to flag baseline deviations with **93% accuracy**, and leverages Google's Gemini API to automatically generate professional dispatch alerts—ensuring public safety while maintaining strict data privacy.

---

## 🧠 Core Architecture

The system is divided into three functional layers:

1. **The Telemetry Pipeline (Data Layer):** Ingests time-series IoT sensor data, applying MinMax scaling and one-hot encoding to spatial constraints.
2. **The Predictive Engine (ML Layer):** A custom TensorFlow LSTM network processes 5-minute sliding windows of 7 distinct temporal and physical features to predict threat probabilities.
3. **The Cognitive UI (GenAI Layer):** Built with Streamlit, the dashboard provides a tactical dark-mode interface. When the LSTM confidence score crosses a user-defined threshold, it triggers Google's Gemini 1.5 Flash model to synthesize the raw anomaly metrics into a human-readable security report.

---

## 📂 Project Structure

```text
├── app.py                     # Main Streamlit dashboard & GenAI integration
├── lstm_model.keras           # Trained TensorFlow LSTM model (93% Test Acc)
├── scaler.pkl                 # Scikit-learn MinMax scaler for real-time input
├── image_metadata.csv         # Sample telemetry data for the UI data-table
├── requirements.txt           # Python dependencies
├── .gitignore                 # Security rules for credentials
└── README.md                  # Project documentation

```

---

## 🛠️ Installation & Local Setup

To run this threat intelligence monitor on your local machine, follow these steps:

**1. Clone the repository:**

```bash
git clone https://github.com/yourusername/UrbanIoT-Threat-Monitor.git
cd UrbanIoT-Threat-Monitor

```

**2. Install dependencies:**
It is recommended to use a virtual environment.

```bash
pip install -r requirements.txt

```

**3. Configure your API Keys:**

* Get a free API key from [Google AI Studio](https://aistudio.google.com/).
* Create a file named `.env` in the root directory.
* Add your key to the file:

```text
GEMINI_API_KEY=your_actual_api_key_here

```

**4. Boot the Dashboard:**

```bash
streamlit run app.py

```

The application will launch in your default web browser at `http://localhost:8501`.

---

## 💻 Usage & Demonstration

1. Open the dashboard and navigate the interactive tabs.
2. Adjust the **Anomaly Sensitivity Threshold** via the sidebar slider. (Lowering the threshold simulates a highly sensitive threat environment).
3. Click **"Run Diagnostics & Predict"**.
4. The system will process a simulated live data sequence through the LSTM. If the output score exceeds your threshold, it will trigger the red alert state and generate a custom Gemini threat summary.

---

## 👨‍💻 Author

**Divyanshu Prajapat** *B.Tech Student | Cybersecurity & Deep Learning Enthusiast* Focusing on vulnerability analysis, secure architecture, and practical AI applications.

---

*Developed for the GenAI Academy APAC Edition Hackathon (July 2026).*
