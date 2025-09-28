# 🎵 LoopLib — Intelligent Audio Loop Sharing Platform

LoopLib is a **web-based platform for musicians and producers** to upload, analyze, and share audio loops with **automated metadata extraction**.  
Unlike platforms that rely on manual tagging (e.g., Splice, Looperman), LoopLib uses **machine learning & signal processing** to automatically detect:

- 🎼 **Key** (Krumhansl–Schmuckler algorithm + chroma features)
- 🥁 **Tempo (BPM)**
- 🎹 **Instrument content** (YAMNet deep learning model)
- 🎧 **Genre classification** (Random Forest / CNN)
- 🔑 **Audio fingerprinting** for unique track identification

It’s built with **React**, **Flask**, **Firebase Authentication**, and **AWS S3** for a secure and scalable user experience.

---

## 🚀 Features

- **Seamless Audio Upload** — drag & drop files, auto-analyzed in seconds.
- **Automated Metadata Extraction** — BPM, key, genre & instruments detected without manual input.
- **Smart Search & Filtering** — find loops by genre, BPM, key, or instrument.
- **User Profiles & Libraries** — organize and manage your personal loop collection.
- **Waveform Visualization** — interactive preview of audio files.
- **Cloud-Based Storage** — scalable & reliable file storage on AWS S3.
- **Secure Authentication** — login with email/password or Google/Facebook via Firebase.
- **Audio Fingerprinting** — generate unique, robust IDs for uploaded loops.

---

## 🏗️ System Architecture


---

## 🛠️ Tech Stack

| Layer              | Technologies |
|--------------------|-------------|
| **Frontend**       | React, React Router, Axios, Tailwind/Material UI |
| **Backend**        | Flask (Python), RESTful APIs |
| **Authentication** | Firebase Authentication (email/password + social logins) |
| **Storage**        | AWS S3 (secure bucket structure per user) |
| **Database**       | Firebase Firestore |
| **Audio Analysis** | Librosa, NumPy, SciPy |
| **Machine Learning** | Random Forest (scikit-learn), CNN (TensorFlow/Keras), YAMNet |
| **Project Management** | Jira, Agile methodology |

---

## ⚡ Machine Learning Components

- **Key Detection:**  
  Krumhansl–Schmuckler algorithm + chroma CENS features (Librosa).
- **BPM Detection:**  
  Multi-step tempo analysis using HPSS, onset strength, autocorrelation & tempograms.
- **Genre Classification:**  
  - Random Forest on MFCCs, chroma, spectral contrast.  
  - CNN on Mel-spectrograms (used for benchmarking).
  - Trained with the **FMA-Small dataset** (balanced 8-genre subset).
- **Instrument Detection:**  
  YAMNet (pre-trained on Google AudioSet) with hierarchical vocal/instrument detection.
- **Audio Fingerprinting:**  
  Beat-synchronized, key-invariant chroma vectors hashed with SHA-256.

---

## 📦 Installation & Setup

> Requires **Python 3.9+** and **Node 18+**.

### 1️⃣ Clone the Repositories
LoopLib is organized into multiple repos:
- **Frontend:** `https://github.com/<your-org>/looplib-frontend`
- **Backend:** `https://github.com/<your-org>/looplib-backend`
- **Genre Classifier:** `https://github.com/<your-org>/looplib-genre-classifier`
- (Optional) Organization-level meta-repo.

```bash
git clone https://github.com/<your-org>/looplib-frontend.git
git clone https://github.com/<your-org>/looplib-backend.git
git clone https://github.com/<your-org>/looplib-genre-classifier.git
```
cd looplib-backend
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
pip install -r requirements.txt

flask run

