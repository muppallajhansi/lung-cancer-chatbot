# lung-cancer-chatbot
Multilingual AI chatbot for lung cancer detection using CT scans.
# 🧠 Lung Cancer Detection Chatbot

An end-to-end intelligent medical assistant that detects lung cancer from CT scan images and generates multilingual, patient-friendly medical reports. Built using deep learning, NLP, and image validation models, this chatbot improves early detection and accessibility for patients worldwide.

-----------------------------------------------------------

## Features

- Swin Transformer for predicting malignancy scores (regression) from lung CT scans  
- ViT + CLIP to validate uploaded images and reject non-lung or non-medical images  
- Meta's NLLB for translating medical reports into 50+ languages  
- BioBERT for answering health-related questions in natural language  
- Streamlit chatbot interface for real-time interaction  
- Exportable PDF reports with malignancy score, risk level, and next steps  
- Doctor consult link for follow-up via telehealth

---------------------------------------------------------

## 📁 Project Structure

lung-cancer-chatbot/
│
├── docs/ → Documentation and setup
│ ├── Documentation Guide.txt
│ ├── Installation Guide.txt
│ └── requirements.txt
│
├── demos/ → Demo video
│ └── chatbot_and_models_demo.mp4
│
├── models/ → Pre-trained models
│ ├── swin_lung_cancer.pth
│ └── vit_lung_classifier.pth
│
├── src/ → Python source files
│ ├── app.py
│ ├── swin transformer.py
│ └── vit.py
│
├── data/ → Final dataset
│
├── results/ → Prediction results, logs
│
├── presentation/ → Slides and reports
│ └── Lung Cancer Chatbot.ppt
│
├── .gitattributes → Git LFS configuration
├── .gitignore → Git ignore rules
└── README.md → Project overview 


---------------------------------------------------------

## Model Overview

- Model: Swin Transformer Tiny  
- Input: 224×224 axial CT slices (PNG format)  
- Output: Continuous malignancy score (regression)  
- Loss: Mean Squared Error (MSE)  
- Optimizer: Adam (lr = 1e-4)  
- Dataset: LIDC-IDRI (First 100 patients)  
- Preprocessing: DICOM → PNG + Histogram Equalization
-----------------------------------------------------------

## Model Evaluation Metrics 

| Metric | Score     |
|--------|-----------|
| MSE    | 0.0192    |
| MAE    | 0.0500    |
| R²     | 0.9872    |


---------------------------------------------------------

## 🚀 How to Run the Project

### 1. Clone the Repository 

git clone https://github.com/<your-username>/lung-cancer-chatbot.git
cd lung-cancer-chatbot


### 2. Install Dependencies 

python -m venv venv
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

### 3. Run the Application 

python src/app.py


Visit http://localhost:5000 in your browser to use the chatbot.

---------------------------------------------------------

## Reference Models

- https://arxiv.org/abs/2103.14030 (Swin Transformer)
- https://arxiv.org/abs/1901.08746 (BioBERT)
- https://openai.com/research/clip (CLIP)
- https://ai.facebook.com/research/no-language-left-behind/ (NLLB-200)
- https://wiki.cancerimagingarchive.net/display/Public/LIDC-IDRI (LIDC-IDRI Dataset)

----------------------------------------------------

## License

This project is open-source under the MIT License.

----------------------------------------------------


## Acknowledgments

Thanks to the open-source community and public datasets like LIDC-IDRI for making this possible.