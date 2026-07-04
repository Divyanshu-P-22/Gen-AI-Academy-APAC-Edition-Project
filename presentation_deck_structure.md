# UrbanIoT Threat Intelligence Center (Deck Content)
**Note:** Use this content to fill out the official `Prototype Submission Deck _ Gen AI Academy APAC Edition.pptx` template.

---

## Slide 1: Participant Details
* **Participant Name:** [Your Name]
* **Problem Statement:** Track 1 (Quantiphi) - AI-powered Decision Intelligence Platform

## Slide 2: Brief about the idea
* **Idea:** The UrbanIoT Threat Intelligence Center is an interactive, multimodal Smart City diagnostic dashboard. It processes raw telemetry flow from city sensors, executes deep-learning anomaly detection using an LSTM network, and delivers actionable, human-readable intelligence via Google Gemini. Instead of just visualizing data, it acts as an operational command center for city managers.

## Slide 3: Solution Explanation
* **Approach:** We approached the problem by treating smart city data (e.g., foot traffic) as a temporal sequence. We ingested the dataset, engineered time-based features, and trained an LSTM model using TensorFlow. When an anomaly is detected, the raw metadata is passed to the **Gemini 1.5 Flash API**, which acts as an Intelligent Assistant to summarize the event.
* **Real-world impact:** City managers are drowning in raw IoT data. This solution bridges the gap between raw telemetry and human action, allowing non-technical stakeholders to understand and act on complex infrastructural anomalies immediately.
* **Core Architecture:** Data Ingestion -> Temporal Preprocessing -> LSTM Neural Network -> GenAI Stakeholder Summarization -> Streamlit Dashboard.

## Slide 4: Opportunities & USP
* **How different is it? (USP):** 
  1. **Privacy-Preserving Proof:** Unlike systems that require invasive CCTV processing, this system uses pure flow metadata, explicitly displaying the telemetry to prove no PII is collected.
  2. **Interactive Tuning:** It features a dynamic LSTM sensitivity threshold knob, acknowledging that real-world AI models require human-in-the-loop tuning for false positives.

## Slide 5: List of features offered
1. **Live Diagnostics:** Real-time calculation of total logs, active threats, and system safety scores.
2. **Interactive Threshold Knob:** Manual tuning of anomaly detection sensitivity.
3. **Temporal Traffic Analysis:** Interactive Plotly charts mapping crowd density over time with anomalies flagged in red.
4. **GenAI Stakeholder Assistant:** A chat interface linked to Gemini to translate flagged raw telemetry into actionable English reports.
5. **Raw Telemetry Tab:** Explicit rendering of metadata flows for transparency.
6. **Model Diagnostics:** Live rendering of LSTM training/validation loss curves to prove model authenticity.

## Slide 6: Process flow / Use-case diagram
* *(Insert a diagram here showing this flow)*:
  1. **User (City Manager)** views Dashboard.
  2. **Dashboard** streams IoT Data.
  3. **LSTM Model** flags data points `> threshold` as anomalies.
  4. **Gemini API** receives flagged data and generates an English summary.
  5. **User** reads summary and clicks "Execute Protocol".

## Slide 7: Wireframes/Mock diagrams
* *(Insert screenshots of your app's layout before it was finished, or early sketches if you have them. Alternatively, map out the layout: Sidebar on the left for parameters, 3 Tabs on the right for Command UI, Telemetry, and Diagnostics).*

## Slide 8: Architecture diagram
* *(Insert a technical architecture block diagram)*
  * `[ Kaggle Dataset ]` -> `[ Pandas / Scikit-Learn ]` 
  * `[ Pandas ]` -> `[ TensorFlow / Keras (LSTM) ]`
  * `[ LSTM ]` -> `[ Streamlit Community Cloud ]`
  * `[ Google Gemini API ]` <-> `[ Streamlit ]`

## Slide 9: Technologies / Services used
* **Google Gemini API:** Used for the GenAI Intelligent Assistant to translate JSON logs into human-readable triage reports.
* **TensorFlow / Keras:** Used to build and train the Sequential LSTM network for deep-learning anomaly detection.
* **Streamlit Community Cloud:** Chosen for rapid frontend deployment and native Python integration.
* **Scikit-Learn:** Used for crucial ML preprocessing, including `MinMaxScaler` and `compute_class_weight` to handle dataset imbalances.
* **Why this stack?** It natively supports the Python data-science ecosystem while providing the scalability to deploy instantly via Streamlit Cloud and seamlessly connect to Google's GenAI endpoints.

## Slide 10: Snapshots of the prototype
* *(Take 3-4 screenshots of your live app running locally or on Streamlit Cloud)*
  1. Screenshot of the Main "Command UI" tab showing the Live Metrics and Chart.
  2. Screenshot of the Gemini chat interface showing a generated intelligence report.
  3. Screenshot of the "Raw Telemetry" tab showing the red-highlighted anomalies.
  4. Screenshot of the "Model Diagnostics" tab showing the loss curves.

## Slide 11: Thank You
* *(Leave as is or add your contact/GitHub link)*
