# UrbanIoT Threat Intelligence Center 🛡️
**Track 1: Quantiphi - AI-powered Decision Intelligence Platform**

Welcome to the UrbanIoT Threat Intelligence Center, an interactive, multimodal Smart City diagnostic dashboard built to process telemetry flow, execute deep-learning anomaly detection, and deliver actionable GenAI intelligence. 

This is not your average SaaS dashboard. It is a Threat Intelligence command center built from the ground up to handle raw telemetry without collecting PII (Personally Identifiable Information).

## 🚀 The Mission
Modern cities are complex networks of utilities, transport, and communication. This project aims to synthesize metadata from urban IoT networks to flag anomalies in real-time. By linking an LSTM (Long Short-Term Memory) model to the Google Gemini Generative AI Engine, this command center not only detects anomalies but also provides context, triage instructions, and stakeholder-ready reports.

## 🛠️ Architecture & Data Flow

```text
[ Urban IoT Dataset ] ──> [ Preprocessing & Vectorization ] ──> [ LSTM Neural Network ]
                                                                        │
[ B.Tech Streamlit UI ] <── [ Gemini GenAI Engine (Vertex AI) ] <───────┘
```

1. **Data Layer (Telemetry):** We ingest `image_metadata.csv` representing smart city logs (e.g., foot traffic patterns, time, location). No PII is collected—just flow metrics.
2. **Preprocessing Layer:** Built with `pandas` and `scikit-learn` to normalize and group sequential data into time-series windows.
3. **ML Engine (LSTM):** A Deep Learning model built with `TensorFlow/Keras`. It learns baseline behaviors over time. When behavior deviates significantly from the baseline, it is flagged.
4. **GenAI Layer:** Google Gemini 1.5 Flash generates dynamic, human-readable intelligence reports based on the raw telemetry surrounding an anomaly.
5. **Presentation Layer:** An authentic, interactive "B.Tech Engineering" Streamlit UI, separating flashy live metrics from hardcore model diagnostics.

## 🌟 Key Features

- **Interactive Threshold Knobs:** Real-time LSTM sensitivity tuning. Showcases that ML models require human-in-the-loop tuning for false positives.
- **Raw Telemetry Tab:** Explicitly displays the metadata flow and highlights rows that cross the LSTM sensitivity threshold, proving the system is analyzing raw metrics, not magic.
- **Model Diagnostics:** Live rendering of the LSTM's training/validation loss curves.
- **Actionable UI Buttons:** "Execute Protocol" and "Flag False Positive" buttons to emulate triage in a real operations center.
- **GenAI Stakeholder Assistant:** A built-in chat interface interacting directly with Gemini to translate raw logs into actionable English summaries.

## 💻 Getting Started (Local Development)

### 1. Clone & Setup
```bash
git clone https://github.com/yourusername/urbaniot-threat-intel.git
cd urbaniot-threat-intel
```

### 2. Environment Configuration
Create a `.env` file in the root directory (or use the provided template) and add your Gemini API Key:
```
GEMINI_API_KEY=your_api_key_here
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Train the LSTM Engine
Upload `train_model.ipynb` and `image_metadata.csv` to Google Colab to clean the data, train the LSTM network, and generate the `lstm_model.keras` and `scaler.pkl` artifacts. Download those artifacts back into this folder.

### 5. Launch the Command Center
Start the Streamlit dashboard:
```bash
streamlit run app.py
```

## ☁️ Deployment (Streamlit Community Cloud)
This project is optimized for direct deployment via Streamlit Community Cloud.
1. Push this repository to GitHub.
2. Log into [share.streamlit.io](https://share.streamlit.io/).
3. Deploy directly from the `app.py` file.
4. Add your `GEMINI_API_KEY` to the App Settings -> Secrets.

## 📋 Hackathon Deliverables Checklist
- [x] **Working Prototype:** Streamlit Community Cloud App.
- [x] **GitHub Repo:** This repository.
- [ ] **Presentation Deck:** (To be added to `docs/` folder)
- [ ] **Demo Video:** (To be linked here)
- [x] **Brief Description:** Included in this README.

---
*Built with ❤️ by a 4th-year B.Tech Engineering student.*
