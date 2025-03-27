# **RT-DETR on UAV Thermal Image Dataset**

This repository contains the implementation and training setup for **RT-DETR (Real-Time DEtection Transformer)** on a **UAV-based thermal image dataset**. The goal is to fine-tune RT-DETR for **thermal object detection** in aerial imagery.

## **Table of Contents**  
- [Introduction](#introduction)  
- [Dataset](#dataset)  
- [Installation](#installation)  
- [Training](#training)  
- [Evaluation](#evaluation)  
- [Results](#results)  
- [Acknowledgments](#acknowledgments)  

---

## **Introduction**  

RT-DETR is a real-time object detection model based on **DEtection Transformers (DETR)**. This project adapts it to **thermal UAV imagery** for tasks such as **human detection, vehicle tracking, and anomaly detection** in aerial thermal data.

---

## **Dataset**  

The dataset consists of **thermal images captured by UAVs**, annotated with bounding boxes. It includes:  
- **Infrared (IR) images** captured in various conditions.  
- **Annotations** in COCO format.  
- **Multiple object classes** (e.g., humans, vehicles, animals).  

📌 **Ensure your dataset is structured as follows:**  
```
/dataset  
    ├── images/  
    │   ├── train/  
    │   ├── val/  
    │   ├── test/  
    ├── annotations/  
    │   ├── train.json  
    │   ├── val.json  
    │   ├── test.json  
```

---

## **Installation**  

Clone the repository and install the required dependencies:  
```bash
git clone https://github.com/your-username/rt-detr-uav-thermal-image-dataset.git  
cd rt-detr-uav-thermal-image-dataset  
pip install -r requirements.txt  
```

---

## **Training**  

Run the training script in the Jupyter Notebook or from the command line:  
```bash
python train.py --epochs 200 --img-size 640 --batch-size 16 --optimizer adamw --lr 0.0001 --momentum 0.937
```

📌 **Key training settings:**  
- **Model:** Pre-trained RT-DETR  
- **Epochs:** 200  
- **Image size:** 640  
- **Optimizer:** AdamW  
- **Learning rate:** 0.0001  

---

## **Evaluation**  

Evaluate the trained model on the validation set:  
```bash
python evaluate.py --model weights/best.pt --data dataset/val.json
```

📌 **Metrics reported:**  
- **mAP (Mean Average Precision)**  
- **Precision & Recall**  
- **Inference speed**  

---

## **Results**  

✅ **Expected outcomes:**  
- Improved detection accuracy in thermal UAV imagery.  
- High-speed inference suitable for real-time applications.  
- Robust performance across different environmental conditions.  

---

## **Acknowledgments**  

This project is based on **RT-DETR by Ultralytics**, adapted for **UAV-based thermal detection tasks**.  

🚀 **Contributions and feedback are welcome!**
