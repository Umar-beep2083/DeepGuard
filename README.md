# DeepGuard: Audio Forensics & Deepfake Detection 🎙️🛡️

> **STATUS: IN PROGRESS 🚧**
> This project is currently in the active development and local testing phase. The Convolutional Neural Network (CNN) architecture has been structured, but model weights are waiting to be trained on the highly anticipated ASVspoof 2019 dataset.

---

## 📖 The Problem
With the rapid acceleration of Generative AI, audio deepfakes and voice cloning attacks (such as CEO fraud and social engineering scams) have reached unprecedented levels. Traditional cybersecurity defenses often fail to detect synthetic audio payloads over phone networks or VoIP software. 

## 🚀 The Solution
**DeepGuard** acts as an advanced audio forensics firewall. Rather than analyzing audio signals purely as temporal data, DeepGuard mathematically transforms audio frequencies into visual **Mel-Spectrograms**. By treating sound as a 2D image, we can deploy hardcore Computer Vision techniques—specifically deep Convolutional Neural Networks (CNNs)—to detect the micro-artifacts and synthetic anomalies left behind by AI voice generators, things that the human ear cannot possibly perceive.

## 🧠 Methodology & Architecture
1. **Audio Ingestion**: Audio files (`.wav`, `.flac`) are uploaded securely via a Streamlit interface.
2. **Feature Extraction**: The `librosa` Python library runs a Fourier Transform to generate Mel-frequency cepstral coefficients (MFCCs).
3. **Deep CNN Classification**: The spectrogram image matrix (128x128x1) is passed through a 3-block Deep Keras CNN architecture featuring heavy Batch Normalization, Max Pooling, and Dropout to prevent overfitting.
4. **Binary Output**: A final Sigmoid activation layer outputs a confidence score determining if the audio is **REAL** or a **DEEPFAKE**.

## 💻 Technical Stack
* **Language**: Python 3.10+
* **Deep Learning Engine**: TensorFlow & Keras
* **Audio Processing**: Librosa & NumPy
* **Frontend Visualization**: Streamlit & Matplotlib

## 🛣️ Project Roadmap
- [x] Establish Base Repo Architecture
- [x] Engineer the `librosa` spectrogram parser
- [x] Fully architect the tf.keras CNN layout
- [ ] Connect and partition the ASVspoof 2019 Dataset
- [ ] Execute `model.fit()` training loops and validate F1 Score
- [ ] Save `.h5` model weights and integrate seamlessly into the Streamlit WebApp
