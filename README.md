# 🏍️ AI Helmet Detection System | YOLOv5

An AI-powered computer vision project that detects whether motorcycle riders are wearing helmets using **YOLOv5**. The system can analyze images, videos, and real-time webcam footage to identify helmet and no-helmet cases, helping support road safety monitoring and intelligent surveillance applications.

---

## 🚀 Project Overview

Road safety is a major concern, especially when riders travel without helmets. This project uses deep learning and object detection to automatically identify helmet usage in visual data.

Using a custom-trained YOLOv5 model, the system detects objects in images and video streams and classifies them according to the trained dataset classes, such as:

- 🪖 Helmet
- ❌ No Helmet

The model can be used for image-based detection, video analysis, and real-time webcam inference.

---

## ✨ Features

- **Custom Object Detection** – Train YOLOv5 on a custom helmet detection dataset.
- **Helmet Detection** – Detect helmet usage in images and video.
- **No-Helmet Detection** – Identify riders detected without helmets.
- **Real-Time Detection** – Run inference using a webcam.
- **Video Analysis** – Process recorded video files.
- **Custom Dataset Support** – Use your own annotated dataset.
- **Deep Learning Based** – Built using PyTorch and YOLOv5.
- **CPU Support** – Can run without a GPU, although inference and training may be slower.

---

## 🧠 How It Works

The system follows a computer vision pipeline:

1. Input an image, video, or live webcam feed.
2. The YOLOv5 model processes the input.
3. The model detects objects and predicts their classes.
4. Bounding boxes and class labels are displayed on detected objects.
5. The processed output is saved for further analysis.

```text
Image / Video / Webcam
          │
          ▼
    Input Processing
          │
          ▼
   Custom YOLOv5 Model
          │
          ▼
 Object Detection & Classification
          │
          ▼
 Bounding Boxes + Class Labels
          │
          ▼
   Detection Results
```

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python | Programming language |
| YOLOv5 | Object detection model |
| PyTorch | Deep learning framework |
| OpenCV | Image and video processing |
| NumPy | Numerical operations |

---

## 📁 Project Structure

```text
helmet-detection-project/
│
├── yolov5/                 # YOLOv5 framework
│
├── train/
│   ├── images/
│   └── labels/
│
├── valid/
│   ├── images/
│   └── labels/
│
├── test/
│   ├── images/
│   └── labels/
│
├── data.yaml               # Dataset configuration
├── README.md
└── ...
```

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/saurabhsingh72487-hub/helmet-detection-projet.git
cd helmet-detection-projet
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

### 3. Activate the Virtual Environment

**Windows:**

```bash
venv\Scripts\activate
```

### 4. Install Dependencies

```bash
cd yolov5
pip install -r requirements.txt
```

---

## 📊 Dataset Configuration

The dataset is organized into training, validation, and testing sets.

### Dataset Structure

```text
train/
├── images/
└── labels/

valid/
├── images/
└── labels/

test/
├── images/
└── labels/
```

### `data.yaml`

```yaml
path: ..

train: train/images
val: valid/images
test: test/images

nc: 2
names:
  - helmet
  - no_helmet
```

> Update the class names and number of classes according to your dataset annotations.

---

## 🎯 Model Training

Train the custom object detection model using YOLOv5:

```bash
python train.py --img 320 --batch 1 --workers 0 --epochs 50 --data ../data.yaml --weights yolov5s.pt
```

### Training Parameters

| Parameter | Value | Description |
|---|---:|---|
| Image Size | 320 | Input image resolution |
| Batch Size | 1 | Number of images per batch |
| Epochs | 50 | Number of training iterations |
| Model | YOLOv5s | Pretrained model used for transfer learning |
| Weights | `yolov5s.pt` | Initial pretrained weights |

The trained model and training results are saved in:

```text
yolov5/runs/train/
```

The best model weights are typically saved at:

```text
yolov5/runs/train/exp/weights/best.pt
```

> The experiment folder name (`exp`, `exp2`, `exp3`, etc.) may vary depending on previous training runs.

---

## 🔍 Inference & Detection

### 🖼️ Detect Helmets in an Image

```bash
python detect.py --weights runs/train/exp/weights/best.pt --source image.jpg
```

### 📹 Detect Helmets in a Video

```bash
python detect.py --weights runs/train/exp/weights/best.pt --source video.mp4
```

### 📷 Real-Time Webcam Detection

```bash
python detect.py --weights runs/train/exp/weights/best.pt --source 0
```

Detection results are saved in:

```text
yolov5/runs/detect/
```

---

## 📈 Model Results

The model's performance can be evaluated using standard object detection metrics:

- **Precision** – How many predicted detections were correct.
- **Recall** – How many actual objects the model successfully detected.
- **mAP (Mean Average Precision)** – Overall object detection performance.
- **Inference Speed** – How quickly the model processes an image.

### Results

_Add your actual training results here._

| Metric | Result |
|---|---|
| Precision | TBD |
| Recall | TBD |
| mAP@0.5 | TBD |
| mAP@0.5:0.95 | TBD |

---

## 🎥 Demo

_Add screenshots or GIFs demonstrating helmet and no-helmet detection here._

Example:

```text
Input Image → YOLOv5 Detection → Bounding Boxes & Labels
```

You can add screenshots of:

- Riders wearing helmets
- Riders without helmets
- Webcam detection
- Video detection output

---

## 💡 Applications

This project demonstrates how AI-powered computer vision can be applied to:

- Road safety monitoring
- Traffic surveillance
- Helmet compliance monitoring
- Smart city applications
- Intelligent transportation systems
- Automated video surveillance

---

## 🔮 Future Improvements

- Improve accuracy with a larger and more diverse dataset.
- Experiment with different YOLO model variants.
- Optimize inference for real-time performance.
- Integrate with CCTV surveillance systems.
- Develop a dashboard for monitoring detection results.
- Extend the system to detect additional traffic violations.

---

## ⚠️ Limitations

- Detection accuracy depends on dataset quality and diversity.
- Occlusion, lighting conditions, camera angles, and distance may affect performance.
- The model should not be considered a fully reliable enforcement system without extensive testing and validation.

---

## 📚 Acknowledgments

This project uses the [YOLOv5](https://github.com/ultralytics/yolov5) object detection framework developed by Ultralytics.

---

## 👨‍💻 Author

**Saurabh Singh**

GitHub: [@saurabhsingh72487-hub](https://github.com/saurabhsingh72487-hub)

---

⭐ If you find this project interesting, feel free to explore the repository!
