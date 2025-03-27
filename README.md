# **RT-DETR on UAV Thermal Image Dataset**

This repository contains the implementation and training setup for **RT-DETR (Real-Time DEtection Transformer)** on a **UAV-based thermal image dataset**. The goal is to fine-tune RT-DETR for **thermal object detection** in aerial imagery.

## **Table of Contents**  
- [Introduction](#introduction)  
- [Dataset](#dataset)    
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
    ├── Train Set/  
    │   ├── images/  
    │   ├── annotations/    
    ├── Validation Set/  
    │   ├── images/  
    │   ├── annotations/  
    ├── Test Set/  
    │   ├── images/  
    │   ├── annotations/
    ├── data.yaml/ 
```


---

## **Training**  

Run the training script in the Jupyter Notebook or from the command line:  
```bash
# Load a model
model = RTDETR('rtdetr-l.pt')

#optimizer = torch.optim.AdamW(model.parameters(), lr=0.001)

# Fine-tune
results = model.train(data='path to/data.yaml', epochs=200, imgsz=640, optimizer='AdamW', lr0=0.0001, momentum=0.937)
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
model = RTDETR('path to /weights/best.pt')
# Run the evaluation
results = model.val(data="path to /data.yaml")

# Print specific metrics
print("Class indices with average precision:", results.ap_class_index)
print("Average precision for all classes:", results.box.all_ap)
print("Mean average precision at IoU=0.50:", results.box.map50)
print("Mean recall:", results.box.mr)
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
