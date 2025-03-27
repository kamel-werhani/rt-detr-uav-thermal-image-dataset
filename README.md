# **RT-DETR on UAV Thermal Image Dataset**

his repository contains the implementation and training setup for **YOLOv12** on a **UAV-based thermal image dataset**. The goal is to fine-tune YOLOv12 for **thermal object detection** in aerial imagery.


## **Table of Contents**  
- [Introduction](#introduction)  
- [Dataset](#dataset)    
- [Training](#training)  
- [Evaluation](#evaluation)  
- [Results](#results)  
- [Acknowledgments](#acknowledgments)  

---

## **Introduction**  

YOLOv12 (You Only Look Once version 12) is a state-of-the-art object detection model designed for real-time applications. This project applies YOLOv12 to **thermal UAV imagery** for tasks such as **human detection, vehicle tracking, and anomaly detection** in infrared aerial data.

---

## **Dataset**  

The dataset consists of **thermal images captured by UAVs**, annotated with bounding boxes. It includes:  
- **Infrared (IR) images** captured in various conditions.  
- **Annotations** in COCO format.  
- **Multiple object classes** (e.g., humans, vehicles, animals).  

📌 **Ensure your dataset is structured as follows:**  
```
/dataset  
    ├── Train Set/  
    │   ├── images/  
    │   ├── annotations/    
    ├── Validation Set/  
    │   ├── images/  
    │   ├── annotations/  
    ├── Test Set/  
    │   ├── images/  
    │   ├── annotations/
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
