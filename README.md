
# 🐔 Poultry Disease Detection Based on YOLOv5

A deep learning system for automated detection and classification of poultry diseases from fecal images using YOLOv5 object detection. The project includes a full pipeline from data annotation to model training and a Flask-based web application for real-time inference.

---

## 📌 Overview

Poultry disease outbreaks can cause significant economic losses in the agricultural sector. Early and accurate detection is critical. This project leverages YOLOv5, one of the most efficient real-time object detection architectures, to detect and classify poultry diseases from fecal images — enabling fast, non-invasive diagnosis.

The system is deployed as a lightweight web application where users can upload an image and receive instant disease detection results.

---

## 🚀 Features

- Real-time poultry disease detection using YOLOv5
- Full training pipeline with custom dataset (annotated via Roboflow)
- Pre-trained model weights (`best.pt`) included for immediate inference
- Flask web application for browser-based image upload and detection
- Docker support for easy deployment
- Clean modular codebase with separate training, detection, and validation scripts

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| Object Detection | YOLOv5 |
| Deep Learning | PyTorch, TensorFlow |
| Data Annotation | Roboflow |
| Web Framework | Flask |
| Frontend | HTML, CSS, JavaScript |
| Containerization | Docker |
| Language | Python 3.8+ |

---

## 📁 Repository Structure

```
Poultry-Disease-Detection-based-on-YOLOv5/
│
├── app.py                  # Flask web application (main entry point)
├── train.py                # Model training script
├── detect.py               # Inference / detection script
├── val.py                  # Model validation script
├── export.py               # Model export utilities
├── best.pt                 # Pre-trained YOLOv5 model weights
├── requirements.txt        # Python dependencies
├── Dockerfile              # Docker configuration
│
├── data/                   # Dataset configuration and images
├── models/                 # YOLOv5 model architecture files
├── utils/                  # Utility functions
├── static/                 # Frontend static files (CSS, JS)
├── templates/              # HTML templates for Flask app
├── runs/                   # Training outputs and detection results
└── instance/uploads/       # Uploaded images via web app
```

---

## ⚙️ Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Nishith170217/Poultry-Disease-Detection-based-on-YOLOv5.git
cd Poultry-Disease-Detection-based-on-YOLOv5
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the Web Application

```bash
python app.py
```

Then open your browser at `http://localhost:5000` — upload a poultry fecal image and get instant detection results.

---

## 🐳 Docker Deployment

```bash
# Build the Docker image
docker build -t poultry-detection .

# Run the container
docker run -p 5000:5000 poultry-detection
```

---

## 🧠 Model Training

To retrain the model on your own dataset:

```bash
python train.py --img 640 --batch 16 --epochs 50 --data data/dataset.yaml --weights yolov5s.pt
```

Pre-trained weights (`best.pt`) are included in the repository for immediate inference without retraining.

---

## 🔍 Run Detection on an Image

```bash
python detect.py --weights best.pt --img 640 --source your_image.jpg
```

Results are saved to the `runs/detect/` folder.

---

## 📊 Model Validation

```bash
python val.py --weights best.pt --data data/dataset.yaml --img 640
```

---

## 📦 Dataset

The dataset was annotated using [Roboflow](https://roboflow.com/) and consists of poultry fecal images labeled across disease categories. The data pipeline includes:

- Image collection and cleaning
- Annotation using bounding boxes in Roboflow
- Dataset export in YOLOv5 format
- Augmentation during training

---

## 🔮 Future Improvements

- Expand dataset with more disease categories
- Integrate Transformer-based detection (RT-DETR)
- Add confidence score threshold controls in web UI
- Mobile-friendly interface for on-farm use
- REST API endpoint for programmatic access

---

## 👤 Author

**Nishith Ranjan Biswas**
M.Sc. Artificial Intelligence — FAU Erlangen-Nürnberg
[GitHub](https://github.com/Nishith170217) · [LinkedIn](https://linkedin.com/in/nishithrb)

---

## 📄 License

This project is licensed under the GPL-3.0 License — see the [LICENSE](LICENSE) file for details.
