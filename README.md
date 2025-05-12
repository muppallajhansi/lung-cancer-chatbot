# Lung Cancer Detection Chatbot

An end-to-end intelligent medical assistant that detects lung cancer from CT scan images and generates multilingual, patient-friendly medical reports. Built using deep learning, NLP, and image validation models, this chatbot improves early detection and accessibility for patients worldwide.

---

## Features

-  **Swin Transformer**: Predicts malignancy scores (regression) from lung CT scans.
-  **ViT + CLIP**: Validates uploaded images to reject non-lung or non-medical images.
-  **Meta's NLLB**: Translates medical reports into 50+ languages.
-  **BioBERT**: Answers health-related questions in natural language.
-  **Streamlit Interface**: Real-time chatbot interaction.
-  **Exportable Reports**: PDF output with malignancy score, risk level, and recommendations.
-  **Doctor Link**: Integration for telehealth follow-up.

---

##  Project Structure

```
lung-cancer-chatbot/
├── docs/           → Documentation and setup
├── demos/          → Demo videos
├── models/         → Pre-trained models
├── src/            → Python source files
├── data/           → Final dataset
├── results/        → Prediction results, logs
├── presentation/   → Slides and reports
└── README.md       → Project overview
```

---

##  Model Overview

- **Model**: Swin Transformer (Tiny)
- **Input**: 224×224 axial CT slices (PNG format)
- **Output**: Continuous malignancy score
- **Loss Function**: Mean Squared Error (MSE)
- **Optimizer**: Adam (learning rate = 1e-4)
- **Dataset**: LIDC-IDRI (First 100 patients)
- **Preprocessing**: DICOM → PNG + Histogram Equalization

---

##  Model Evaluation Metrics

| Metric | Score  |
|--------|--------|
| MSE    | 0.0192 |
| MAE    | 0.0500 |
| R²     | 0.9872 |

---

##  How to Run the Project

1. **Clone the Repository**
```bash
git clone https://github.com/<your-username>/lung-cancer-chatbot.git
cd lung-cancer-chatbot
```

2. **Install Dependencies**
```bash
python -m venv venv
# On Windows
venv\Scripts\activate
# On macOS/Linux
source venv/bin/activate
pip install -r requirements.txt
```

3. **Run the Application**
```bash
python src/app.py
```

---

## Reference Models

- [Swin Transformer](https://arxiv.org/abs/2103.14030)
- [BioBERT](https://arxiv.org/abs/1901.08746)
- [CLIP](https://openai.com/research/clip)
- [Meta NLLB-200](https://ai.facebook.com/research/no-language-left-behind/)
- [LIDC-IDRI Dataset](https://wiki.cancerimagingarchive.net/display/Public/LIDC-IDRI)

---

##  License

This project is open-source under the [MIT License].

---

##  Acknowledgments

Special thanks to the open-source community and public datasets like LIDC-IDRI for enabling this work.
