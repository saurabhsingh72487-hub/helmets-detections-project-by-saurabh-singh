# YOLOv5 Object Detection Project

Custom object detection project built using YOLOv5.

## Features
* Custom YOLOv5 training.
* Image detection
* Webcam detection
* Video inference
* Custom dataset support
* PyTorch based implementation

---

# Project Structure

```text
yolov5-project/
│
├── yolov5/
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
├── data.yaml
└── README.md
```

---

# Installation

## Clone Repository

```bash
git clone https://github.com/saurabhsingh72487-hub/helmet-detection-projet.git
cd yolov5-project
```

## Create Virtual Environment

```bash
python -m venv venv
```

## Activate Environment

### Windows

```bash
venv\Scripts\activate
```

---

# Install Requirements

```bash
cd yolov5
pip install -r requirements.txt
```

---

# Dataset Configuration

`data.yaml`

```yaml
path: C:/Users/saaur/yolov5-project

train: train/images
val: valid/images
test: test/images

nc: 2
names: ["class1", "class2"]
```

---

# Training

```bash
python train.py --img 320 --batch 1 --workers 0 --epochs 50 --data C:/Users/saaur/yolov5-project/data.yaml --weights yolov5s.pt
```

---

# Detection

## Image Detection

```bash
python detect.py --weights runs/train/exp8/weights/best.pt --source image.jpg
```

## Webcam Detection

```bash
python detect.py --weights runs/train/exp8/weights/best.pt --source 0
```

## Video Detection

```bash
python detect.py --weights runs/train/exp8/weights/best.pt --source video.mp4
```

---

# Output

## Training Output

```text
runs/train/
```

## Detection Output

```text
runs/detect/
```

---

# Model

Best trained model:

```text
runs/train/exp8/weights/best.pt
```

---

# Technologies Used

* Python
* PyTorch
* YOLOv5
* OpenCV
* NumPy

---

# Notes

* CPU training supported
* GPU recommended for faster training
* Increase epochs and dataset size for better accuracy

---

# License

This project uses the YOLOv5 framework by Ultralytics.
